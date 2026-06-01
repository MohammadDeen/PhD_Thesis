# PaperBanana Setup Protocol
# GPP Research Figure Generation Environment

**Author:** Deen Fortune  
**Date:** 2026-06-01 (last updated 2026-06-01)  
**Platform:** Linux x86_64 (Ubuntu 18.04-era kernel, GCC 7 — C++20 not supported)  
**Repo:** `llmsresearch/paperbanana` (cloned to `/home/sbsuser/Deen/paperbanana`)

---

## 1. Prerequisites

### System requirements
- Python 3.10+ — system Python was 3.6/3.8; used conda base (Python 3.11.4)
- conda available at `/home/sbsuser/anaconda3`
- Internet access for pip and Google Gemini API calls

### Check available Python versions
```bash
# System Python (too old — 3.6.9)
python3 --version

# conda base has 3.11.4 — use this
/home/sbsuser/anaconda3/bin/python --version
```

---

## 2. Create Virtual Environment

Use the conda base Python 3.11.4 to create a project-local venv. Do NOT use the
system Python 3.6 — it is below the required 3.10 minimum.

```bash
cd /home/sbsuser/Deen/paperbanana

/home/sbsuser/anaconda3/bin/python -m venv .venv

# Activate (run this every session)
source .venv/bin/activate
```

---

## 3. Upgrade pip, setuptools, wheel

```bash
python3 -m pip install --upgrade pip setuptools wheel
```

---

## 4. Install PaperBanana

### Why not `pip install -e ".[dev,google,pdf]"`?
The `dev` extra includes `pymupdf>=1.24`, which requires C++20 to compile from source.
The system GCC (7.x) does not support C++20. This causes a build failure.

### Solution: install in stages

**Step 1 — core + Google provider:**
```bash
pip install -e ".[google]"
```

**Step 2 — dev tools (without pymupdf):**
```bash
pip install pytest pytest-asyncio pytest-cov ruff
```

**Step 3 — pymupdf via pre-built binary wheel (pinned version with confirmed wheel):**
```bash
pip install "pymupdf==1.23.26"
```
The `manylinux2014_x86_64` wheel installs without compilation.
Do NOT use `pip install 'paperbanana[pdf]'` directly — it pulls latest pymupdf which
tries to build from source on this system.

**Step 4 — Studio (Gradio web UI):**
```bash
pip install 'paperbanana[studio]'
```

**Step 5 — graphviz system binary (for SVG/PDF vector export):**
```bash
sudo apt-get install graphviz

# Verify
which dot
```

---

## 5. Verify Installation

```bash
# CLI works
paperbanana --help

# Core import
python3 -c "import paperbanana; from paperbanana.core.config import Settings; print('OK:', Settings().vlm_provider)"

# PDF support
python3 -c "import fitz; print('pymupdf OK:', fitz.__version__)"

# Vector export
which dot

# Studio
paperbanana studio --help
```

### Run the test suite (safe — no API calls needed)
```bash
# Skip PDF-specific tests (they need pymupdf features; optional)
pytest tests/ \
  --ignore=tests/test_core/test_pdf_extract.py \
  --ignore=tests/test_core/test_pdf_pages_spec.py \
  --ignore=tests/test_pdf_dep_check.py \
  -q --tb=no
```

Expected result: ~684 passed, 4 failed (`test_cli.py::test_setup_*` — unrelated to
generation; these are wizard UI tests), 10 skipped.

---

## 6. Configure API Keys

```bash
cp .env.example .env
```

Edit `.env`:

```bash
# Google Gemini (recommended — free tier available)
GOOGLE_API_KEY=your_key_here
GOOGLE_BASE_URL=                              # leave blank for official API
GOOGLE_VLM_MODEL=gemini-2.5-flash            # NOTE: gemini-2.0-flash no longer
GOOGLE_IMAGE_MODEL=gemini-2.0-flash-exp-image-generation  # available to new keys
```

Get a Gemini API key at https://aistudio.google.com — no credit card required.

### Important: model availability for new API keys
`gemini-2.0-flash` is **not available to new API keys** (as of 2026-06-01). You will
get a `404 NOT_FOUND` error if you use the default config. Always override with:
```
GOOGLE_VLM_MODEL=gemini-2.5-flash
GOOGLE_IMAGE_MODEL=gemini-2.0-flash-exp-image-generation
```

If unsure which models your key can access:
```bash
python3 -c "
from google import genai
import os
from dotenv import load_dotenv
load_dotenv()
client = genai.Client(api_key=os.environ['GOOGLE_API_KEY'])
for m in client.models.list():
    print(m.name)
" 2>&1 | grep -i flash
```

### Security warning: never use `--verbose`
The `--verbose` flag causes the rich traceback renderer to dump full Python stack frame
locals on error. These locals include the `HttpRequest` object, which contains your
API key in the `x-goog-api-key` header. Use `--progress-json` instead for safe
progress output.

```bash
# UNSAFE — exposes API key in tracebacks
paperbanana generate ... --verbose

# SAFE — structured JSON progress, no stack frames
paperbanana generate ... --progress-json
```

If you accidentally expose your key, rotate it immediately at https://aistudio.google.com.

---

## 7. GPP Research Files

The following files were created for GPP PhD research figure generation.

### Create the examples directory
```bash
mkdir -p examples/deen-gpp-figures/data
```

### Files created

| Path | Purpose |
|------|---------|
| `docs/deen-scientific-figure-workflow.md` | Full workflow guide and style guide |
| `examples/deen-gpp-figures/gpp-il36-neutrophil-pathway.txt` | IL-36/NF-κB/neutrophil pathway |
| `examples/deen-gpp-figures/wes-to-variant-prioritization-workflow.txt` | WES variant discovery pipeline |
| `examples/deen-gpp-figures/pbmc-to-osteoclast-differentiation-workflow.txt` | PBMC→osteoclast protocol |
| `examples/deen-gpp-figures/ptgs1-cox1-pge2-functional-assay.txt` | COX-1→PGE2 biochemistry + assay |
| `examples/deen-gpp-figures/rna-seq-skin-neutrophil-analysis-overview.txt` | RNA-seq pipeline overview |
| `examples/deen-gpp-figures/smMIP-targeted-sequencing-workflow.txt` | smMIP sequencing workflow |
| `examples/deen-gpp-figures/data/burden-test-forest-plot.json` | **MOCK** burden test data |
| `examples/deen-gpp-figures/batch_manifest.yaml` | Batch manifest for all 6 diagrams |
| `examples/deen-gpp-figures/plot_batch_manifest.yaml` | Batch manifest for statistical plots |
| `examples/deen-gpp-figures/README.md` | Quick reference |

---

## 8. Batch Generation with SVG Output

### `--vector-export` is NOT available on `paperbanana batch`
Only `paperbanana generate` supports `--vector-export`. Running:
```bash
paperbanana batch --manifest ... --vector-export svg   # ✗ fails
```
gives: `No such option '--vector-export'`

### `--progress-json` is also NOT available on `paperbanana batch`
Only `paperbanana generate` supports `--progress-json`. Running:
```bash
paperbanana batch --manifest ... --progress-json       # ✗ fails
```
gives: `No such option '--progress-json'`

### Solution: pass vector_export via a config YAML file

Create `configs/gpp_batch_config.yaml`:
```yaml
vlm:
  provider: gemini
  model: gemini-2.5-flash

image:
  provider: google_imagen
  model: gemini-2.0-flash-exp-image-generation

pipeline:
  vector_export: svg
```

Then run batch with `--config`:
```bash
paperbanana batch \
  --manifest examples/deen-gpp-figures/batch_manifest.yaml \
  --config configs/gpp_batch_config.yaml \
  --format png
```

This produces both `final_output.png` and `final_output.svg` for every item in the batch.

### Options available on `paperbanana batch`
```
--manifest / -m       path to YAML/JSON manifest (required)
--output-dir / -o     parent output directory (default: outputs)
--config              path to config YAML (use for vector_export)
--vlm-provider        VLM provider override
--vlm-model           VLM model override
--image-provider      image gen provider override
--image-model         image gen model override
--iterations / -n     refinement iterations per item
--auto                loop until critic satisfied
--max-iterations      safety cap for --auto
--optimize            preprocess inputs
--format / -f         png, jpeg, or webp
--save-prompts        save prompts per run (default: on)
--venue               target venue style
--concurrency         parallel workers (default: 1)
--resume-batch        resume a previous batch by ID or path
--retry-failed        retry failed items on resume
--verbose / -v        show detailed progress
--quiet / -q          suppress per-item status table
```

---

## 9. First Successful Run

### Command (safe — no `--verbose`)
```bash
paperbanana generate \
  --input examples/deen-gpp-figures/gpp-il36-neutrophil-pathway.txt \
  --caption "IL-36 signalling pathway in GPP: IL36RN LOF drives uncontrolled NF-κB activation, CXCL1/CXCL8 release, and neutrophil recruitment. CARD14 GOF and AP1S3 LOF as secondary inputs." \
  --format png \
  --progress-json
```

### Output
```
run_id:   run_20260601_100137_8ebd27
output:   outputs/run_20260601_100137_8ebd27/final_output.png
duration: 333s (~5.5 minutes)
cost:     $0.0062 actual (Google billing) / $0.0133 PaperBanana estimate
```

### Output directory contents
```
final_output.png       — best iteration (use this)
diagram_iter_1.png     — iteration 1
diagram_iter_2.png     — iteration 2
diagram_iter_3.png     — iteration 3
iter_1/ iter_2/ iter_3/— per-iteration prompts and metadata
planning.json          — planner and stylist decisions
metadata.json          — full run metadata (model, cost, timing)
run_input.json         — saved input for --continue-run
prompts/               — all agent prompts sent to the API
```

---

## 9. Installed Package Versions (as of 2026-06-01)

| Package | Version | Purpose |
|---------|---------|---------|
| paperbanana | 0.1.2 | Core package |
| google-genai | 2.7.0+ | Gemini VLM + image provider |
| pymupdf | 1.23.26 | PDF input support |
| gradio | 6.15.2 | Studio web UI |
| pytest | 8.0+ | Test suite |
| ruff | 0.4+ | Linting |
| graphviz (system) | — | SVG/PDF vector export |

---

## 10. Feature Status After Setup

| Feature | Command | Status |
|---------|---------|--------|
| Diagram generation | `paperbanana generate` | ✓ |
| Statistical plots | `paperbanana plot` | ✓ |
| Batch diagrams | `paperbanana batch` | ✓ |
| Batch plots | `paperbanana plot-batch` | ✓ |
| PDF input | `--input file.pdf` | ✓ (pymupdf 1.23.26) |
| SVG vector export | `--vector-export svg` | ✓ (graphviz) |
| PDF vector export | `--vector-export pdf` | ✓ (graphviz) |
| Studio web UI | `paperbanana studio` | ✓ (gradio 6.15.2) |
| Run continuation | `--continue-run <id>` | ✓ |
| Input optimisation | `--optimize` | ✓ (use after confirming quota) |

---

## 11. Session Activation (every new terminal)

```bash
cd /home/sbsuser/Deen/paperbanana
source .venv/bin/activate
```

---

## 12. Common Issues Encountered and Fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| `pymupdf` build fails | System GCC too old (no C++20) | `pip install "pymupdf==1.23.26"` (pre-built wheel) |
| `404 NOT_FOUND gemini-2.0-flash` | Model unavailable to new API keys | Set `GOOGLE_VLM_MODEL=gemini-2.5-flash` in `.env` |
| `429 RESOURCE_EXHAUSTED` | Free tier rate/daily limit hit | Remove `--optimize`; wait for quota reset (midnight PT) |
| API key exposed in terminal | `--verbose` dumps HTTP headers in tracebacks | Always use `--progress-json` instead of `--verbose` |
| SVG export silently skipped | `graphviz dot` not on PATH | `sudo apt-get install graphviz` |
| `cd final_output.png` error | `cd` is for directories, not files | `cd outputs/run_<id>/` then `ls` |
| `--vector-export` not found on batch | Flag only exists on `generate` | Use `--config configs/gpp_batch_config.yaml` with `pipeline.vector_export: svg` |
| `--progress-json` not found on batch | Flag only exists on `generate` | Use `--verbose` or just omit (batch prints its own status table) |
