# Automated Muscle Fiber Detection and Myonuclei Quantification

This repository contains a Python-based image analysis pipeline for detecting and quantifying muscle fibers and associated myonuclei from histological images. Given paired annotated and unannotated images, the pipeline selects a fixed number of high-quality, non-adjacent fibers using geometric and spatial constraints, detects associated nuclei, and produces both quantitative outputs and annotated visualizations.

Annotated example images visualize the same fiber selection used for downstream quantification, ensuring that visual outputs are faithful to the underlying analysis.

---

## Features

- Automated detection of muscle fiber boundaries
- Forced selection of high-quality, non-adjacent fibers
- Association of detected myonuclei to selected fibers
- Quantitative output of fiber- and image-level metrics
- Annotated visual outputs for qualitative inspection
- Fully runnable from the command line (no notebooks required)

---

## Demo Data

The `data/` directory contains two small demonstration datasets:

- `demo_unquantified.zip`: raw, unannotated histological images  
- `demo_quantified.zip`: corresponding annotated images used for pairing and validation  

These datasets are intentionally small and are provided solely to demonstrate the pipeline’s functionality.

---

## Installation

Create and activate a virtual environment, then install dependencies:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Usage

Run the pipeline on the included demonstration data:

```bash
python3 finalfinalqacclean_github_native.py \
  --quantified_zip data/demo_quantified.zip \
  --unquantified_zip data/demo_unquantified.zip \
  --n 5
```
The --n flag controls how many image pairs are processed.
If omitted, the pipeline will process all matched image pairs in the provided datasets.


---

## Outputs

Running the pipeline creates an `outputs/` directory containing:

- **predictions.csv**  
  Quantitative measurements computed from the selected muscle fibers and associated myonuclei.

- **annotated_*.png**  
  Annotated images showing the automatically selected, non-adjacent fibers and detected nuclei overlaid on the raw images.

The annotated images visualize the *same fibers used for quantification*, ensuring that visual outputs faithfully represent the underlying analysis.


## System Dependency: Tesseract OCR

This project uses Tesseract OCR via the `pytesseract` Python package.  
The Tesseract engine itself must be installed separately.

### macOS
```bash
brew install tesseract
```
### Ubuntu / Debian
```bash
sudo apt-get install tesseract-ocr
```
If Tesseract is not installed, the pipeline may fail or skip OCR-related steps.

### Credits
Collaborators: Leo Farina, Leo Ha, Paul Terry, Ethan Dangel
Coding: Leo Farina, Leo Ha


