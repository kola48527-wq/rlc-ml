# RLC Circuit Resonance Analysis with Machine Learning

## Project Overview
This project applies Machine Learning to predict the behavior of an RLC circuit under alternating current. The pipeline generates a synthetic dataset based on impedance formulas, visualizes amplitude-frequency characteristics, and trains regression models to predict the maximum current (Imax) based on circuit parameters (R, L, C, U).

## Objective
To develop a Machine Learning model capable of predicting the maximum current (resonance) of an RLC circuit, and to evaluate the model's robustness against simulated real-world data noise and outliers.

## Physics Background
In an RLC circuit, resonance occurs when inductive and capacitive reactances cancel each other out. The total impedance equals the active resistance, and the current reaches its maximum.

* Resonance frequency: w0 = 1 / sqrt(L * C)
* Maximum current: Imax = U / R

## Tech Stack
* Language: Python 3
* Data Processing: Pandas, NumPy
* Machine Learning: Scikit-learn (Random Forest), LightGBM
* Visualization: Matplotlib

## Results
The models were trained on a dataset of over 160,000 combinations.

* Baseline (Random Forest, clean data): R2 = 0.8900
* Tuned Model (LightGBM, clean data): R2 = 0.9906
* Tuned Model (LightGBM, combined noise & outliers): R2 = 0.9600

**Robustness Test:**
To simulate real-world sensor imperfections, Gaussian noise and 1% random outliers were injected into the dataset. While the standard MSE loss caused the R2 score to drop to 0.75, applying a robust objective function (Huber loss) and outlier filtering restored the accuracy to R2 = 0.96. This proves the model's reliability for industrial applications with noisy data.

## Repository Structure
* rlc_dataset.ipynb - Generates the synthetic dataset based on physical equations, including noise and outlier injection.
* rlc_graphs.ipynb - Visualizes the resonance curves (amplitude-frequency characteristics).
* rlc_model.ipynb - Trains the LightGBM model, evaluates performance, and handles noisy data.
* requirements.txt - Required Python libraries.
* .gitignore - Excludes large data files and generated graphs from the repository.

## How to Run
1. Clone the repository:
   git clone https://github.com/kola48527-wq/rlc-ml.git

2. Install the required dependencies:
   pip install -r requirements.txt

3. Run the notebooks in order: rlc_dataset.ipynb -> rlc_graphs.ipynb -> rlc_model.ipynb

## Author
Forkol
* 13-year-old ML Enthusiast and Developer
* GitHub: @forkoll
