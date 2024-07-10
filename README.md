# JWST-passage-Quiescent-galaxies
Using JWST-NIRISS F115 &amp; F120W grism spectroscop to identify quiescent galaxies, selected on morphology via supervised machine-learning trained upon SDSS imaging and validate with independent JWST


# Project setup

Prerequisites
- Python 3
- Git


1. Clone the repository
```bash
git clone https://github.com/it-guy007/JWST-passage-Quiescent-galaxies.git
cd JWST-passage-Quiescent-galaxies
```
2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`
```
3. Install the requirements 
```bash
pip install -r requirements.txt
```
4. Create the folder structure:
```
JWST-passage-Quiescent-galaxies
├── data
│   ├── images_training_rev1
│   ├── training_solutions_rev1.csv
│   └── converted
│
├── tf_data
│   ├── one_one
│   └── one_two
└── models
```
5. Download the data from the Kaggle competition [Galaxy Zoo - The Galaxy Challenge](https://www.kaggle.com/c/galaxy-zoo-the-galaxy-challenge/data) and place it in the data folder

 Alternatively, you can use the Kaggle API to download the data:
 ```bash
 kaggle competitions download -c galaxy-zoo-the-galaxy-challenge -p data/
 unzip data/galaxy-zoo-the-galaxy-challenge.zip -d data/
 ```

# Model creation
The [notebook](notebooks/model_builder_sequential.ipynb)  has all the logic required for creating the model. Modify the needed variables for needed extra configuration.

# Model analytics
The [notebook](notebooks/model_builder_analysis.ipynb) has all the logic for evaluating the model and creating the needed plots for analysis.

# Running predictions
The [notebook](notebooks/model_predictor_batch.ipynb) has all the logic for using the model to create predictions of fits files. It generates a csv with the predictions stored for further analysis and if activated a separate directory with the images desired above a certain accuracy.

# Analytics of the predictions
The [notebook](notebooks/model_predictor_analytics.ipynb) has all the logic for evaluating the predictions and creating the needed plots for analysis.

# Downloading model
It is also possible to download a pre-trained model for this project, which are the steps done in the [builder notebook](notebooks/model_builder_sequential.ipynb). The model is available at [Hugging Face](https://huggingface.co/IT-Guy007/AstroVisionV1). Move both files in data to the local model folder of the project.

# License
This project is licensed under the MIT License see the [LICENSE](LICENSE) file for details.