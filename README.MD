# Astronomical Object Classification

A machine-learning pipeline for classifying astronomical objects from Sloan Digital Sky Survey (SDSS) imagery, photometric data, and spectra.

The project explores multiple models rather than treating astronomical classification as a single task: image-based galaxy/star classification, color-index approaches for galaxy/QSO separation, and spectral classification of stars into the **O, B, A, F, G, K, M** classes.

## Approach

- **Image classification:** PyTorch CNN trained on SDSS image data
- **Galaxy/QSO experiments:** decision-tree and SVM classifiers using photometric color indices
- **Stellar classification:** 1D Inception-style CNN operating on normalized wavelength/flux spectra
- **Evaluation:** train/validation/test workflows, cross-validation, classification reports, and confusion matrices
- **Data pipeline:** scripts for SDSS retrieval, preprocessing, dataset splitting, and normalization

## Project Structure

```text
src/
├── data_fetch/   # SDSS data acquisition
├── data_prep/    # preprocessing and dataset preparation
├── model/        # model definitions and training scripts
└── evaluation/   # evaluation utilities
```

`notebooks/` contains exploratory work, while `models/` and `logs/` contain saved outputs from training runs.

## Setup

Python 3.11 is recommended.

```bash
git clone https://github.com/GrantDeljevic/AstronomicalObjectsClassifier_new.git
cd AstronomicalObjectsClassifier_new
python -m venv .venv
```

Activate the environment, then install dependencies:

```bash
pip install -r requirements.txt
```

Example training entry points:

```bash
python -m src.model.train
python -m src.model.starClassClassifier
```

The datasets are large and are not stored directly in the repository. Some research scripts also assume the project's original local data layout and may require path configuration before running on a new machine.

## Project Materials

- [Dataset archive](http://astronomical-objects-classifier-ml-cs-5821-sp-2024-team-nasa.s3-website-us-east-1.amazonaws.com/)
- [Final report](https://docs.google.com/document/d/1ZDG7YZVYs-TmtAimgGl4OibZnr7c_fC4FXyD6RzGKCQ/edit?usp=sharing)
- [Final presentation](https://docs.google.com/presentation/d/1Z-0BezzBDLCYE0P_Ll5b5kaQxfcwy_4iyZT_5lS9gHY/edit?usp=sharing)
