# U‑Net Cell Segmentation

## Dataset Notice </br>
This project uses the BCCD Dataset with Masks, published on Kaggle by Jeet B. Lahiri.
The dataset is not included in this repository.

Dataset link:
https://www.kaggle.com/datasets/jeetblahiri/bccd-dataset-with-mask

The dataset is distributed under the MIT License.
Users should refer to the original Kaggle page for full licence terms and authorship information.

## Overview </br>

The notebook implements:

* deterministic preprocessing (resizing, normalisation, dataset splitting)

* training‑only augmentation using Albumentations

* a standard U‑Net encoder–decoder with skip connections

* combined Binary Cross‑Entropy + Dice loss

* evaluation using Dice, IoU, precision, and recall

* qualitative visualisation of predictions vs ground truth


## Results </br>
The model achieves stable optimisation and produces masks closely aligned with ground‑truth annotations.
Limitations and potential extensions (e.g., instance segmentation, uncertainty estimation) are discussed in the notebook.



This repository is released under the MIT License.
