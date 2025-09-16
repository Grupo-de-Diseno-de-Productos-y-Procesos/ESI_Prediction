[![DOI](https://zenodo.org/badge/286865245.svg)](https://zenodo.org/badge/latestdoi/286865245)

# Enzyme-Substrate Interaction (ESI) Prediction

![Introduction to the ESI Prediction Model](https://raw.githubusercontent.com/lfsalasnu/Specific_CPI/main/Problem_general.png)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/your-repo-name/blob/main/ESI_Prediction.ipynb)
_Click the badge to run this project directly in Google Colab._

---

## Model Introduction

This project implements a machine learning model to predict **Enzyme-Substrate Interactions (ESI)**. The model, based on the use of protein sequence descriptors, has proven to be effective for identifying enzymes that mediate reactions of biotechnological interest. This methodology has been successfully applied to various enzyme families, including **Cytochrome P450 (CYP)**, **N-Methyltransferases**, and **Oxidoreductases**.

Studies with this model have covered both plant organisms, such as **plants**, and **microorganisms**, allowing for the discovery of new enzymes and the understanding of their metabolic roles.

---

## Key Features

* **Feature Engineering:** Protein sequences are transformed into **47 robust numerical descriptors**. These descriptors include physicochemical encodings, Position-Specific Scoring Matrices (PSSM), and n-grams.
* **Modeling:** An **ensemble learning** model is used to combine predictions and improve accuracy.
* **Optimization:** Includes hyperparameter optimization with **Grid Search** to ensure optimal performance.

### Machine Learning Model

<img src="https://raw.githubusercontent.com/lfsalasnu/Specific_CPI/main/Model.png" alt="Figure 2" width="800"/>

---

## Reproducing Results

1.  **Create the Conda environment:**  
    Create a virtual environment with the following core dependencies:    
      
    `python=3.11 scikit-learn pandas jupyter blast bioconductor-kebabs=1.24.0`

2.  **Install additional packages:**
    Once the environment is created, activate it and install `ifeatpro`, `ngrampro`, and `pssmpro` using `pip`.
    `$ conda activate te_env`
    `$ pip install ifeatpro`
    `$ pip install ngrampro`
    `$ pip install pssmpro`

3.  **Reproducing ESI Prediction Results**
    The `ESI_Prediction.ipynb` notebook in the `notebooks/` directory provides step-by-step instructions on how we obtained the current results. Simply open a Jupyter session and run the cells in order. The training data and the `utils` folder must be uploaded.

    **Important:** Some steps, such as generating PSSM profiles, can take several hours to run. To speed up the process, using multiple cores is recommended.

4.  **Applying this Model to Other Protein Sequence Classification Problems**
    You can adapt this pipeline to other protein sequence classification applications as follows:

    * **Prepare your database:** Create a training and a test dataset in the same format as the `.csv` files in the `data/raw/` directory. The format should be:
        * **Training dataset:** `protein_name, protein_sequence, protein_label`
        * **Test dataset:** `protein_name, protein_sequence`
    * **Adapt the Notebook:** Duplicate the `ESI_Prediction.ipynb` notebook and rename it for your application. Modify the `train_raw` and `test_raw` variables in the notebook to point to your new files.
    * **Run the Notebook:** Follow the steps in the notebook.

---

## How to Use

1.  **Clone the repository:**
    ```
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  **Run in Colab:**
    The easiest way is to click the "Open In Colab" badge at the beginning of the file. Follow the steps in the `ESI_Prediction.ipynb` notebook to load data, process sequences, train the model, and evaluate its performance.