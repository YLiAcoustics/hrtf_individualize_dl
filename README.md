Note: this repository is forked from the original one by Miccini et al.. I am currently working on addapting the models for modeling individual HRTFs in the near-field, i.e. introducing the source distance as an input parameter. 

Since the authors did not provide the data files, I processed SOFA HRTFs from the CIPIC database so that they are in the proper format required by the DNN models. These include the HRTF, source position and anthropometrics data. The files can be found at https://1drv.ms/u/s!Asa019mjsJgVk0RxlZ2Sm-Ay8fvS?e=wfYIMy (download the folder as a whole and put it inside the folder containing the python files).

Yuqing Li, 02/2023

--------------------------------Contents below this line are from the original repository--------------------------------

# HRTF Individualization using Deep Learning
> Material from paper _HRTF Individualization using Deep Learning_, Miccini and Spagnol, 2020


**UPDATE: This repository if provided for reference only; please check our latest devopments! Take a look at [our new paper](https://itsadive.create.aau.dk/wp-content/uploads/2021/03/SIVE_2021.pdf) and [source code](https://github.com/miccio-dk/itsadive_hybrid_structural_model/) for a fully-functional HRTF individualization solution.**

## Structure

- `utils_data.py`: a collection of functions for loading and processing data (HRTFs, ear pictures, anthropometric measurements, etc)
- `utils_model.py utils_model_1d.py utils_train.py`: a collection of functions for generating and training deep learning models 
- `utils_plot.py`: a collection of functions for showing the results (latent space visualization, comparison of reconstructed HRTFs or ear pictures, correlation matrices, etc)
- a series of Jupiter notebooks, constituting the experiments, where all the aforementioned scripts are used:
  - `vae_hutubs.ipynb`: autoencoding HRTFs (2d elevation-azimuth representation)
  - `vae_hutubs_hrtf.ipynb`: autoencoding HRTFs (2d frequency-elevation representation)
  - `vae_hutubs_gpu1.ipynb`: preliminary experiments with autoencoding pinna depth maps
  - `vae_hutubs_ears.ipynb`: autoencoding pinna depth maps using Inception layers
  - `vae_hutubs_chen2019.ipynb`: autoencoding individual HRTFs using dense or 1D-convolutional layers
  - `vae_hutubs_3d.ipynb`: autoencoding HRTFs patches and reconstructing one-hot representation
  - `pca_dnn.ipynb`: predicting HRTF principal components using anthropometric measurements (k-fold validation)
  - `ear_pca_dnn.ipynb`: predicting HRTF principal components using anthropometric measurements and principal components from pinna depth maps (k-fold validation)


## Instructions

### Setup
- Install `conda` (an environment and dependency manager for Python)
- Create environment: `conda env create -f environment.yml`
- Run Jupyter: `jupyter-lab`

### Usage
Notebooks can be accessed from the browser at `127.0.0.1:8888`.
The cells within the notebooks contains precomputed output related to the latest execution.
However, each notebook has hyperparameters that can be adjusted.
Unfortunately, most notebooks are not entirely polished, presenting unused code, duplicated sections, and various data, reflecting the exploratory and experimental nature of the research.

When attempting to run any of the code, access to the generated datasets is necessary.
If needed, the data can be requested by contacting the paper authors.


**Riccardo Miccini, 2019-2020**

