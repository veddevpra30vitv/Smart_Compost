# main.ipynb Overview

This notebook builds and compares three PyTorch classification models for compost degradation prediction based on the waste catalogue dataset. The goal is to evaluate how well the model can classify compost samples into the target degradation classes when using different representations of the same underlying data:

- Range-based features (minimum and maximum values)
- Midpoint features (central value for each measurement)
- Categorical-band features (coded class bands)

The notebook does the following in sequence:

1. Load the dataset and inspect its structure.
2. Prepare three feature sets by dropping columns that are not relevant to each modelling approach.
3. Convert categorical values into one-hot encoded numeric columns for model training.
4. Split each dataset into training and testing sets.
5. Define a small neural network architecture for classification.
6. Train the model with cross-entropy loss and Adam optimization.
7. Plot training accuracy/loss over time.
8. Generate confusion matrices and accuracy summaries for each model.

This project is a compact experimentation workflow rather than a production pipeline. It is designed to compare model input representations and identify which one performs best for the target class prediction task.

## Key idea

The dataset contains compost-related properties such as moisture, C:N ratio, pH, and other waste attributes. The notebook strips away non-model columns, creates separate views of the data, and trains a neural network to predict the `target_degradation_class_code`.

## Model comparison

The notebook compares:

- Range model: uses `moisture_min`, `moisture_max`, etc.
- Midpoint model: uses `moisture_midpoint`, `cn_ratio_midpoint`, etc.
- Categorical band model: uses band-code representations instead of raw numeric ranges

The final cells plot the learning curves and confusion matrices for these three models so the reader can compare performance visually.
