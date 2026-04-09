# AGENTS.md

## Overview
Static HTML site for math exercises (Lithuanian). Uses a Python script to generate HTML pages from PDFs.

## Key Commands

- **Generate HTML**: `python gen.py` - Scans `pdfs/` folder and generates `index.html` + class pages
- **Add new content**: Place PDFs in `pdfs/{class}/{theme}/` structure, then run `gen.py`

## Structure

- `pdfs/{class}/{theme}/` - PDFs organized by class (e.g., "8 klase") and theme folders
- `gen.py` - Generator script; reads PDF structure and outputs HTML
- `index.html`, `8-klase.html`, `9-klase.html`, `12-klase.html` - Generated files (do not edit manually)

## CI/Deploy

- Push to `main` triggers `.github/workflows/deploy.yml`
- Workflow: runs `python gen.py` → FTP deploys to InfinityFree
- FTP credentials stored in GitHub secrets
