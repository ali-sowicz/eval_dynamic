This repository automates the evaluation of multiple-choice questions generated by large language models. It is organized into three main tasks:

1. **Experiment Execution**: Runs experiments by querying models with various prompting techniques on a test dataset and saving model responses.
2. **Accuracy Computation**: Extracts answer letters from model responses, computes accuracy, and checks format correctness using evaluation metadata.
3. **Manual Correction**: Provides a script to update evaluation metadata (e.g., manually correcting responses that are in the wrong format) and recompute statistics.

## Preparation
Update the config.yaml file with correct paths, prompt type, and GPU id before proceeding.

## Usage
1. **Running Experiments**: To run experiments and generate model responses, execute: 
```python
python -m src.run_experiment
```
This script reads the test datasets (as configured in config.yaml), sends prompts to each model, and saves the responses in the specified output directory.

2. **Computing Accuracy**: After running experiments, compute accuracy by extracting answer letters from responses: 
```python
python -m src.compute_accuracy
```
This script compares extracted letters with the ground truth, computes accuracy, and saves both an evaluation metadata file and an accuracy summary.


3. **Manual Correction**: For cases where responses are in the wrong format, manually update the "extracted_by_hand" field in the evaluation metadata file, then run: 
```python
python -m src.manual_correction
```
This script applies your manual corrections and recomputes the accuracy statistics, saving the updated metadata and new accuracy summary.

