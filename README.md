# Machine Learning needs Better Randomness Standards

## Table of Contents
1. [Overview](#overview)
2. [Getting Started](#getting-started)
    1. [Dependencies](#dependencies)
    2. [Models Used](#models)
    3. [Data Links](#data)
    4. [Flow Chart](#flowchart)
3. [Instruction to Run](#instruction)
4. [Sample output](#sample)


## Overview <a name="overview"></a>
The paper "Machine Learning Needs Better Randomness Standards: Randomised Smoothing and PRNG-Based Attacks" discusses how randomness plays a vital role within ML algorithms, specifically regarding the robustness certification technique of randomised smoothing and its vulnerability to PRNG-based attacks. It also shows how inadequate examination of PRNG quality in these algorithms produces security weaknesses that adversaries can exploit through PRNG-based attacks. The paper develops an evaluation framework to enhance randomness standards in ML applications by using cryptographically secure PRNGs (CSPRNGs) together with advanced statistical testing methods.


## Getting Started <a name="getting-started"></a>


### Dependencies <a name="dependencies"></a>
* Python 3.*
* Libraries: NumPy, Sklearn, scipy, random, hashlib, and nistrng.
* colab

### Models Used <a name="models"></a>
* **Model**: A pre-trained ResNet18 model is adapted for CIFAR-10 by modifying the final fully connected layer to output 10 classes.

### Data <a name="data"></a>
* **Dataset**: CIFAR-10 dataset is used for training and evaluation.

### Flowchart <a name="flowchart"></a>
<p align="center">
  <img src="flow chart.png" alt="Workflow: Input Data → ResNet → Randomised Smoothing → Certified Robustness
                                                                      → PRNG-Based Attacks → Attack Success Rate" width="600">
</p>

## Instruction to Run<a name="instruction"></a>
### Detailed Code Execution 
* Set up and import the libraries
* Load Dataset and Prepare Model like ResNet18
* Define Randomised Smoothing Function - The randomised_smoothing function certifies model robustness by adding noises like **(Laplace, Absolute Normal, Uniform, Bernoulli)** distribution.
* Define PRNG-Based Attack Functions - function simulates adversarial attacks using the generated noise and returns the attack success rate using  **(Negative Kurtosis Attack, Skewness Attack, Positive Kurtosis Attack)**.
* Evaluate Randomness Quality - nist_test function evaluates randomness quality using the NIST SP800-22 test suite and shapiro_wilk_test function tests for normality in the randomness samples using the Shapiro-Wilk test
* Certified Robustness Calculation - The certify_robustness function computes the average certified robustness radius for the entire test dataset using randomised smoothing.
* Evaluate Model Performance - evaluate_model function evaluates the model's performance and robustness using **(Clean Accuracy, Certified Robustness, Attack Success Rates)**.
* Main Execution - Train the Model, Evaluate Randomness Quality, Evaluate Model with Standard PRNG, and Evaluate Model with Cryptographic PRNG.
* Return the output - Model Performance Metrics and Randomness Quality Results.
* How to run: git clone https://github.com/ranjithchodavarapu/Seminar-Project-Code.git
* cd Seminar-Project-Code - navigate into that directory.
  



## Sample Output <a name="sample"></a>




