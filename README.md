Deep Learning PR 1 --- Breast Cancer Classification

Video Overview : https://drive.google.com/drive/folders/1xqZgFuELyQ5X2rAJDmQvpHVH_75xqzHr?usp=sharing

Project Overview

This project is part of Deep Learning PR 1 from Red & White Skill
Education.

The main goal of this project is to understand and implement different
neural network techniques for binary classification using the Breast
Cancer Wisconsin (Diagnostic) Dataset.

The project covers:

Data Scaling

Single-Layer Perceptron (SLP)

Multi-Layer Perceptron (MLP)

Activation Functions

Early Stopping

Dropout

L1, L2 and L1-L2 Regularization

Final combined model

Model comparison and clinical insight

Dataset

Dataset: Breast Cancer Wisconsin (Diagnostic)

Source: sklearn.datasets.load_breast_cancer()

The dataset contains:

569 samples

30 numerical features

212 Malignant cases

357 Benign cases

Target classes:

0 = Malignant

1 = Benign

No CSV download is required because the dataset is directly available
through Scikit-learn.

Technologies Used

Python 3.x

TensorFlow / Keras

Scikit-learn

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

Project Tasks

Task 1 --- Data Loading, EDA & Preprocessing

The dataset is loaded using Scikit-learn.

The following steps are performed:

Load the dataset

Check shape and statistics

Check target class distribution

Create a class distribution plot

Create a feature correlation heatmap

Split data into training and testing sets

Apply StandardScaler

The data is split using:

Test size = 20%

Random state = 42

Stratification = target

StandardScaler is fitted only on the training data to avoid data
leakage.

Task 2 --- Single-Layer Perceptron

A Single-Layer Perceptron is used as the baseline model.

Architecture:

30 Input Features → 1 Sigmoid Output

Configuration:

Optimizer: Adam

Loss: Binary Crossentropy

Epochs: 50

Batch size: 32

The model is evaluated using:

Test accuracy

Classification report

Confusion matrix

Training/validation curves

The SLP provides a baseline because it can learn only a linear decision
boundary.

Task 3 --- Multi-Layer Perceptron & Activation Functions

An MLP is created with the architecture:

30 → 64 → 32 → 1

Three hidden-layer activation functions are compared:

ReLU

Tanh

Sigmoid

The validation accuracy of all three models is compared.

ReLU is generally useful because it allows fast learning and reduces the
vanishing-gradient problem for positive inputs. Tanh is zero-centred but
can suffer from vanishing gradients. Sigmoid is useful for binary output
but can have stronger vanishing-gradient problems in hidden layers.

Task 4 --- Early Stopping

Early Stopping is used to reduce overfitting.

Configuration:

monitor = val_loss
patience = 15
restore_best_weights = True

The model with Early Stopping is compared with an identical model
trained without the callback.

The validation-loss curves are used to observe overfitting and the
effect of Early Stopping.

Task 5 --- Dropout

Dropout is used as a regularization technique.

Dropout rates tested:

0.1

0.3

0.5

Dropout randomly disables a percentage of neuron activations during
training. This helps the network avoid depending too much on individual
neurons and can reduce overfitting.

The validation accuracy of the three dropout rates is compared to select
the best configuration.

Task 6 --- Regularization

Three regularization methods are implemented:

L1 Regularization

L1 = 0.001

L1 can make some weights exactly zero and may therefore perform a form
of feature selection.

L2 Regularization

L2 = 0.001

L2 penalizes large weights and helps create a smoother model that is
less likely to overfit.

L1-L2 Regularization

L1 = 0.0001
L2 = 0.001

L1-L2 combines both regularization methods and is also known as
ElasticNet regularization.

The three models are compared using training/validation loss and test
accuracy.

Task 7 --- Final Combined Model

The final model combines the main techniques that help with
generalization:

L2 Regularization
        +
Dropout 0.3
        +
Early Stopping

Architecture:

30 → 128 → 64 → 1

The hidden layers use ReLU and the output layer uses Sigmoid.

The final model is evaluated using:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

Model Comparison

The notebook contains a complete comparison table with:

Model      Architecture   Regularization   Dropout   Early      Accuracy    Precision   Recall      F1
Stopping

SLP        30-1           None             0         No         Generated   Generated   Generated   Generated
in notebook in notebook in notebook in notebook

MLP-ReLU   30-64-32-1     None             0         No         Generated   Generated   Generated   Generated
in notebook in notebook in notebook in notebook

MLP +      30-128-64-1    None             0         Yes        Generated   Generated   Generated   Generated
Early                                                           in notebook in notebook in notebook in notebook
Stopping

MLP +      30-128-64-1    None             Best rate Yes        Generated   Generated   Generated   Generated
Dropout                                                         in notebook in notebook in notebook in notebook

MLP + L2   30-128-64-1    L2               0         Yes        Generated   Generated   Generated   Generated
in notebook in notebook in notebook in notebook

The exact numerical results should be taken from the final executed
notebook rather than manually entered into the README.

Clinical Insight

For a cancer classification problem, accuracy alone is not enough.

Recall is especially important because a false negative means that a
malignant case may be predicted as benign.

Therefore, when considering a model for clinical decision-support use,
precision and recall should both be considered.

The default classification threshold is 0.5. In a real clinical
system, a lower threshold could be considered to increase sensitivity
and reduce false negatives. However, the actual threshold should be
selected using proper clinical validation.

This project is an educational machine-learning experiment and is not
intended to replace professional medical diagnosis.

Project Structure

DL_PR1/
│
├── DL_PR1.ipynb
├── DL_PR1.html
├── README.md
├── requirements.txt
│
└── plots/
    ├── class_distribution.png
    ├── correlation_heatmap.png
    ├── slp_training_curves.png
    ├── slp_confusion_matrix.png
    ├── activation_comparison.png
    ├── mlp_confusion_matrix.png
    ├── early_stopping.png
    ├── early_stopping_comparison.png
    ├── dropout_comparison.png
    ├── regularization_comparison.png
    ├── accuracy_comparison.png
    └── final_confusion_matrix.png

Requirements

Create a requirements.txt file containing:

tensorflow>=2.12.0
scikit-learn>=1.4.0
pandas
numpy
matplotlib
seaborn

Install the required packages with:

pip install -r requirements.txt

How to Run

Install Python 3.x.

Install the required libraries.

Open Jupyter Notebook.

Open DL_PR1.ipynb.

Run all cells from top to bottom.

Make sure there are no errors.

Restart the kernel and use Run All before submission.

Export the notebook as HTML.

Keep the notebook, HTML file, plots and requirements file in the
GitHub repository.

Video Explanation

A 5--10 minute video explaining the project is required.

The video should explain:

Why StandardScaler is used

SLP vs MLP

ReLU vs Tanh vs Sigmoid

Early Stopping

Dropout

L1 vs L2 Regularization

Clinical precision/recall trade-off

Video Link:
[Add your Google Drive or YouTube Unlisted video link here]

Tools Used

TensorFlow/Keras --- Neural network models

Scikit-learn --- Dataset, preprocessing and evaluation

Pandas --- Data handling

NumPy --- Numerical operations

Matplotlib --- Visualization

Seaborn --- Statistical plots

Jupyter Notebook --- Project development

Conclusion

This project demonstrates how different Deep Learning techniques affect
a binary classification problem.

Starting with an SLP baseline, the project progresses to MLPs and then
applies activation-function comparison, Early Stopping, Dropout and
regularization.

Finally, a combined model using L2 Regularization, Dropout and Early
Stopping is evaluated against the other models.

The project shows the importance of not only achieving high accuracy,
but also controlling overfitting and considering precision, recall and
F1-score for classification performance.

Author 

Purvi Talaviya
