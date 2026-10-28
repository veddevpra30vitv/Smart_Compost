# Smart Composting: ML-Based Compost Degradation Prediction

**Multidisciplinary Project (MDP) | Review 1**

## 1. Project Overview

Composting is an important process for converting organic waste into useful, nutrient-rich material. However, the degradation of organic waste depends on several interacting factors, including moisture content, pH, carbon-to-nitrogen (C:N) ratio, temperature, and the characteristics of the composting materials.

This project explores the application of **Machine Learning (ML) and Neural Networks** to predict compost degradation classes using compost-related parameters.

The objective is to develop a data-driven prototype that can analyze input features and estimate the corresponding degradation class. By exploring different data representations and comparing model performance, the project aims to identify an effective approach for compost degradation prediction.

## 2. Problem Statement

Traditional composting practices often rely on general guidelines and manual observation to assess the decomposition process. These approaches may not always capture the relationships between multiple composting parameters.

This project investigates whether a neural network trained on structured compost data can learn patterns in compost-related features and classify degradation outcomes.

The project focuses on:

- Organizing compost-related data into a structured dataset.
- Preparing numerical and categorical representations of the input features.
- Developing neural network models for multiclass classification.
- Evaluating model performance using appropriate classification metrics.
- Establishing a foundation for a future compost analysis and recommendation interface.

## 3. Project Objectives

1. Create and preprocess a structured dataset containing compost-related parameters.
2. Explore multiple feature representations to understand their effect on prediction performance.
3. Develop feed-forward neural network models using PyTorch.
4. Predict the target degradation class from the prepared input features.
5. Evaluate the models using accuracy, precision, recall, F1-score, loss curves, and confusion matrices.
6. Establish a foundation for integrating the trained models into a user-friendly application in future development stages.

## 4. Methodology

The current implementation follows a machine learning pipeline consisting of the following stages:

### 4.1 Data Preparation

A structured dataset containing 200 records is used for the current prototype. The data is inspected and preprocessed to handle missing values, maintain consistent feature representations, and prepare the target labels for classification.

The target variable is `target_degradation_class_code`, which represents four degradation classes encoded as `0`, `1`, `2`, and `3`.

### 4.2 Feature Representation

Three dataset representations are explored to evaluate how different forms of input data affect model learning.

| Representation | Description |
|---|---|
| Range-based | Represents selected parameters using minimum and maximum values. |
| Midpoint-based | Uses midpoint values to represent parameters that have ranges. |
| Categorical-band | Represents selected parameters using categorical bands and their corresponding numerical encodings. |

Each representation is prepared separately to ensure that its feature structure matches the corresponding model's input layer.

### 4.3 Data Preprocessing

The preprocessing workflow includes:

- Handling missing and non-finite numerical values.
- Converting categorical features into suitable numerical representations.
- Separating input features from the target variable.
- Splitting the dataset into training and testing subsets, using a 90:10 split.
- Applying suitable imputation and feature scaling where required.

The preprocessing parameters should be fitted on the training subset and reused for the corresponding test data and future predictions.

### 4.4 Neural Network Development

Three independent feed-forward neural networks are implemented using PyTorch, with one model for each dataset representation.

The current network architecture consists of:

| Layer | Configuration |
|---|---|
| Input layer | Number of features depends on the dataset representation |
| Hidden layer 1 | 16 neurons, ReLU activation |
| Hidden layer 2 | 8 neurons, ReLU activation |
| Output layer | 4 neurons, one for each degradation class |

The models use a multiclass classification approach with Cross-Entropy Loss and the Adam optimizer.

The output layer produces logits, which are converted into class probabilities using softmax during inference.

### 4.5 Model Evaluation

The models are evaluated using multiple metrics and visualizations:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Reliability of predictions for each class.
- **Loss curves:** Training and test loss across epochs.
- **Accuracy curves:** Training and test accuracy across epochs.
- **Actual vs. predicted plots:** Comparison of actual degradation classes with model predictions.
- **Confusion matrices:** Analysis of correct classifications and misclassifications.

These evaluations help compare the three feature representations and identify areas for further improvement.

## 5. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Dataset manipulation and preprocessing |
| NumPy | Numerical operations |
| Matplotlib | Data visualization and model evaluation plots |
| Scikit-learn | Data splitting, preprocessing utilities, and evaluation metrics |
| PyTorch | Neural network implementation and training |
| Jupyter Notebook | Interactive experimentation and analysis |

## 6. Current Project Status

**Milestone: Review 1 completed**

The project has reached the initial model-development and evaluation stage.

Work completed so far:

- [x] Initial compost dataset preparation.
- [x] Development of three feature representations.
- [x] Data preprocessing and handling of missing values.
- [x] Implementation of three feed-forward neural network models.
- [x] Training of the three models.
- [x] Preparation of model accuracy, loss, and classification visualizations.

The next development stage can focus on making an efficient function of these three models, comparing the models systematically, improving the reliability of the evaluation, and integrating the prediction pipeline into a more accessible interface.

## 7. Next Steps:

Next steps in the project include:

1. **Model comparison and refinement:** Evaluate the three models under consistent conditions and investigate generalization to unseen compost samples.
2. **Expanded dataset:** Incorporate additional records and reliable measurements covering a wider range of composting conditions.
3. **Explainable predictions:** Investigate which parameters have the greatest influence on the model's predictions.
4. **Compost recommendations:** Explore how degradation predictions can be combined with validated composting guidelines to provide practical suggestions.
5. **Experimental validation:** Compare model predictions with observed degradation outcomes to assess real-world reliability.

These extensions are proposed future work and will depend on data availability, validation, and further development.

## 8. Team Members

This project brings together students from computing, chemical engineering, and biotechnology disciplines to explore a multidisciplinary approach to compost analysis.

| S. No. | Team Member | Department / Programme |
|---:|---|---|
| 1 | Ved P | CSE – Data Science |
| 2 | Adwita | CSE – Core |
| 3 | Dhanu | Chemical Engineering |
| 4 | Pranav S | Biotechnology |
| 5 | Keerthana | CSE – Bioinformatics |

## 9. Conclusion

The project establishes an initial machine learning pipeline for compost degradation classification using structured compost-related data. By developing and comparing three neural network models based on different feature representations, the work explores how data preparation can influence classification performance.

The current implementation provides a foundation for further experimentation, model validation, and the development of a practical compost analysis system.

**Project Stage:** Review 1  
**Project Domain:** Machine Learning, Sustainable Waste Management, and Composting  
**Primary Focus:** Neural Network-Based Compost Degradation Classification
