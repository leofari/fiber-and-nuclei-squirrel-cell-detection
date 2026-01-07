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
