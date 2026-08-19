# COMP0192-Velostat-Calibration-Pipeline
This repository contains the data and analysis pipeline developed for my MSc dissertation within the UCL MSc Artificial Intelligence for Biomedicine and Healthcare programme.

The project investigates the calibration of a 4×4 Velostat pressure-sensing array. The notebook covers the complete analysis workflow, from loading and checking the experimental data to model selection, final held-out evaluation and additional sensor-specific analyses.

## Project information
**Author:** Padma Michela Ricca
**Student Number:** 25166236
**Dissertation Title:** Temporal Learning-Based Calibration of a Velostat Pressure-Sensing Array: Mitigating Inherent Artefacts Towards Pressure Ulcer Risk Monitoring in Comatose Patients 
**Programme:** MSc Artificial Intelligence for Biomedicine and Healthcare  
**Department:** Department of Computer Science, University College London (UCL)
**Module Code:** COMP0192 
**Supervisor:** Dr Ben Oldfrey   
**Academic Year:** 2025/26

## Repository contents
- `Velostat_Calibration_Pipeline.ipynb` — notebook containing the complete calibration and modeling pipeline.
- `data.zip` — experimental dataset collected separately during the study and subsequently used by the notebook, available from the `Releases` section of this repository.
- `.gitignore` — excludes temporary Python and Jupyter files from version control.

## Dataset
The dataset contains 12 formal acquisition sessions, with 54 acquisition units per session.

Data collection uses the recorded sensor channels together with the corresponding nominal pressure and spatial ground-truth labels.

The original dataset structure is retained so that the integrity checks and session-level analysis implemented in the notebook can be reproduced directly.

## Analysis pipeline
The notebook includes:
- data loading and integrity checks;
- preprocessing of the 16 sensor channels;
- exploratory analysis of the sessions;
- chronological forward validation and model selection;
- comparison of per-taxel linear, Ridge, MLP, LSTM and GRU models;
- final evaluation on test sessions;
- pressure and spatial prediction metrics; 
- additional analyses of sensor behaviour, including creep, hysteresis, drift and crosstalk.

Generated figures and tables are automatically saved during execution to ensure better quality.

## Running the notebook
The analysis was developed and tested in Google Colab.

1. Download `data.zip` from the Releases section of this repository.
2. Open `Velostat_Calibration_Pipeline.ipynb`.
3. Upload `data.zip` to the `/content/` directory.
4. Run the notebook sequentially from top to bottom.

The notebook extracts the dataset to `/content/data/` and saves generated outputs to `/content/final_results/`.

## Other information
The pipeline uses Python 3 and the following main packages:

- NumPy
- pandas
- Matplotlib
- scikit-learn
- PyTorch

PyTorch uses a CUDA-enabled GPU when available and falls back to the CPU otherwise.

## Reproducibility
Random seeds used during model development and final evaluation are defined explicitly in the notebook. Model selection is performed using chronological forward validation, preserving the temporal ordering of the experimental sessions before final held-out evaluation.

## Use and licensing
This repository is currently provided for academic review and reproducibility of the dissertation work. No open-source licence has been selected; therefore, standard copyright applies.
