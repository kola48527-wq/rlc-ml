# RLC Circuit Resonance Analysis with Machine Learning

## Project Overview
This project applies Machine Learning to predict the behavior of an RLC circuit under alternating current. The pipeline generates a synthetic dataset based on impedance formulas, visualizes amplitude-frequency characteristics, and trains regression models to predict the maximum current (Imax) based on circuit parameters (R, L, C, U).

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
The models were trained on a dataset of over 100,000 combinations.

* Baseline (Random Forest): R2 = 0.89
* Tuned Model (LightGBM): R2 = 0.9906

## Repository Structure
* rlc_dataset.ipynb - Generates the synthetic dataset based on physical equations.
* rlc_graphs.ipynb - Visualizes the resonance curves (amplitude-frequency characteristics).
* rlc_model.ipynb - Trains the LightGBM model and evaluates its performance.
* requirements.txt - Required Python libraries.
* .gitignore - Excludes large data files and generated graphs from the repository.

## How to Run
1. Clone the repository:
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

2. Install the required dependencies:
   pip install -r requirements.txt

3. Run the notebooks in order: rlc_dataset.ipynb -> rlc_graphs.ipynb -> rlc_model.ipynb
