# U‑Net Cell Segmentation
This repository contains a deep-learning pipeline for semantic cell segmentation using a U‑Net architecture trained on the BCCD dataset. The project integrates data preparation, augmentation, model training, evaluation, and post‑segmentation morphological analysis evaluated at both the pixel level and the population level using morphological shape metrics.

## Dataset Notice </br>
This project uses the BCCD Dataset with Masks, published on Kaggle by Jeet B. Lahiri.
The dataset is not included in this repository.

Dataset link:
https://www.kaggle.com/datasets/jeetblahiri/bccd-dataset-with-mask

The dataset is distributed under the MIT License.
Users should refer to the original Kaggle page for full licence terms and authorship information.

## How to Run Notebook </br>
Open unet_bccd_segmentation.ipynb in Google Colab.

Install dependencies using:
```
pip install -r requirements.txt
```
Download the BCCD dataset from Kaggle and place the images and masks in the expected directory structure.

Run the notebook cells sequentially.

## Method Summary </br>

The notebook covers:

* Deterministic preprocessing  
resizing, normalisation, train/validation/test splitting

* Training‑only augmentation  
using Albumentations to introduce realistic variability

* U‑Net encoder–decoder architecture  
with skip connections for spatial detail preservation

* Combined BCE + Dice loss  
for stable optimisation on small biomedical datasets

* Quantitative evaluation  
using Dice, IoU, precision, and recall

* Qualitative visualisation  
comparing predictions with ground‑truth masks

* Post‑segmentation morphological analysis  
using connected‑component labelling to extract instance‑level geometric features
(area, perimeter, circularity, eccentricity)

* Population‑level feature comparison  
assessing whether predicted masks preserve biologically meaningful shape distributions


## Results </br>
Training converges stably and the predicted masks closely match the ground-truth annotations.
Population‑level morphological analysis shows strong agreement in area and circularity distributions, with expected perimeter deviations due to contour smoothing.
These findings demonstrate that the model captures both pixel‑wise accuracy and biologically relevant geometric properties across the test set.

Limitations and potential extensions (including instance‑aware architectures, multi‑dataset training, and uncertainty estimation) are discussed in the notebook.


## Segmentation Viewer App

Ensure dependencies are installed (see instructions above).

Run the viewer:

```
python app/cell_segmentation_viewer.py
```

The app downloads the trained model and processed test data from their public Hugging Face repositories and displays predictions alongside ground‑truth masks.  
Below is a brief demonstration of the Gradio user interface, showing how the model predicts in real-time.



https://github.com/user-attachments/assets/b04e9757-6186-4c65-821c-2bf1eb1fa17c



## Model & Processed Test Set Hosting
The trained U‑Net model and processed test split are hosted on Hugging Face:

Model: best_model.keras

Test Data: X_test.npy, Y_test.npy

These files are automatically retrieved using `hf_hub_download` when the app is launched.

## License </br>
This project is released under the MIT License.
The dataset retains its own licence as indicated in the dataset notice.
