# Machine Learning Regressors for Laryngeal Biomechanical Control

## Description
This repository contains the dataset samples and Jupyter Notebooks necessary to replicate the machine learning regression analysis presented in our research on laryngeal biomechanical control.

The project implements feature-based regressors (Random Forest, Neural Networks, and Polynomial Regression) to approximate the forward mapping from physiological control parameters (muscle activation and subglottal pressure) to acoustic outputs ($f_o$ and SPL). This approach replaces computationally expensive ODE solvers of lumped-element models with fast surrogate models suitable for real-time control frameworks.

## Project Structure

The repository is organized as follows:

- **`data/`**: Contains the datasets generated from the numerical simulations.
  - `dataset_BCM.csv`: Data (subset) generated using the Extended Body-Cover Model (ext-BCM).
  - `dataset_TBCM.csv`: Data generated using the Triangular Body-Cover Model (TBCM).
  
- **Notebooks**:
  - `Regressors_BCM.ipynb`: Jupyter notebook containing the training, validation, and evaluation pipeline for the ext-BCM dataset.
  - `Regressors_TBCM.ipynb`: Jupyter notebook containing the training, validation, and evaluation pipeline for the TBCM dataset.

## Dataset Information

The datasets consist of input-output pairs used to train the forward models.

### Inputs (Control Parameters)
- **$P_s$**: Subglottal pressure (Pa)
- **$a_{CT}$**: Cricothyroid muscle activation (normalized 0-1)
- **$a_{TA}$**: Thyroarytenoid muscle activation (normalized 0-1)
- **$a_{LCA}$**, **$a_{IA}$**, **$a_{PCA}$**: Adductor/Abductor activations (fixed for this model configuration).

### Outputs (Acoustic Targets)
- **$f_o$**: Fundamental frequency (Hz)
- **SPL**: Sound Pressure Level (dB)

## Getting Started

### Prerequisites
To run the notebooks, you will need a Python environment with the following libraries installed:
- `numpy`
- `pandas`
- `scikit-learn`
- `matplotlib`
- `joblib` (optional, for saving models)

### Usage
1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/repo-name.git](https://github.com/jealpape/ML-Regressors-for-Laryngeal-Biomechanical-Control.git)

2. Open:  `Regressors_BCM.ipynb` or `Regressors_TBCM.ipynb` to explore the training process and visualize the results.


## Model References

The datasets were generated using the following lumped-element models:

**ext-BCM (Extended Body-Cover Model):**  
Zañartu M, Galindo GE, Erath BD, Peterson SD, Wodicka GR, Hillman RE. 
Modeling the effects of a posterior glottal opening on vocal fold dynamics with implications for vocal hyperfunction. 
*J Acoust Soc Am.* 2014 Dec;136(6):3262. doi: 10.1121/1.4901714. PMID: 25480072; PMCID: PMC4257958.  


**TBCM (Triangular Body-Cover Model):**  
Alzamendi GA, Peterson SD, Erath BD, Hillman RE, Zañartu M. 
Triangular body-cover model of the vocal folds with coordinated activation of the five intrinsic laryngeal muscles. 
*J Acoust Soc Am.* 2022 Jan;151(1):17. doi: 10.1121/10.0009169. PMID: 35105008; PMCID: PMC8727069.

## Citation

If you use this code or data in your research, please cite the associated paper:

[Placeholder for your Paper Citation: Authors, Title, Journal, Year, DOI]

## Acknowledgment

This research is supported by the National Institutes of Health (NIH) National Institute on Deafness and Other Communication Disorders grant P50 DC015446, ANID grants Becas de Doctorado Nacional 21202490 and 21240471, FONDECYT 1230828 and 3250844, and BASAL AFB240002.
