# Pig Models Notebook README

This README describes the purpose, structure, and usage of the `pig_models.ipynb` notebook. It provides guidance on running the workflow, understanding inputs and outputs, and adapting the code for custom use.

## Overview

The `pig_models.ipynb` notebook contains a complete workflow for preparing Pigeon Lake environmental and satellite data, training predictive models, evaluating model performance, and exporting results. It integrates data ingestion from Google Cloud Storage (GCS), preprocessing, feature engineering, model training, and scoring.
This same code was run on the other lakes in the study by changing the input file names.
## Key Features

* **Google Cloud Storage integration** for reading and writing datasets.
* **Data preparation functions** for cleaning, filtering, merging, and engineering predictors for modeling.
* **Support for multiple machine learning models**, including Random Forest, XGBoost, and deep learning models.
* **Model evaluation utilities** providing metrics, visualizations, and reproducible outputs.
* **Command-line interface (CLI) compatibility**, enabling the notebook script to be run as a standalone module.

## Notebook Structure

### 1. Imports and Setup

Loads standard scientific Python libraries, Google Cloud SDK handlers, and custom utility functions.

### 2. File Management and I/O

Functions to:

* Detect whether a path points to local storage or GCS
* Download and upload files to/from GCS
* Read CSV, Parquet, or model artifacts

### 3. Data Preparation

Includes:

* Cleaning raw sensor and satellite datasets
* Handling missing values
* Creating time-lagged predictors
* Merging environmental and remote-sensing data

### 4. Model Training

Implements multiple modeling approaches such as:

* Random Forest
* XGBoost
* BN
* ConvLSTM

### 5. Model Evaluation

Computes standard performance metrics, including:

* Precision, Recall, F1
* ROC-AUC
* PR-AUC

### 6. Export

Trained models, processed datasets, and metrics are saved to GCS or local directories.

## Usage

### Running in Google Cloud Workbench

1. Open the notebook in your Workbench environment.
2. Ensure your service account has read/write access to required buckets.
3. Run notebook cells in sequence.
4. Modify file paths to match your project structure.

### Running as a Python Script

The notebook includes a `main()` function and argument parser, allowing execution as:

```bash
python pig_models.ipynb --input_data <path> --output_dir <path> --model <model_type>
```

Convert the notebook to a script if needed:

```bash
jupyter nbconvert --to script pig_models.ipynb
```

## Requirements

* Python 3.9+
* Google Cloud SDK
* pandas, numpy, scikit-learn
* xgboost, tensorflow (if using deep learning models)

## Customization

* Update file paths to point to your buckets or datasets.
* Modify model hyperparameters inside the model training section.
* Add new evaluation metrics or export formats as needed.

## Notes

* Ensure environment variables and credentials are correctly configured for GCS operations.
* Large datasets may require increasing memory allocation in Workbench.

## License

This project is provided as-is for academic and research purposes. Modify freely for your own work.
