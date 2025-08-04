# Ayna_Project
# Polygon Coloring with UNet

## Description
This repository contains a Collab notebook that trains a UNet model to color the interiors of polygon shapes based on user-selected colors. The project includes both training and inference pipelines, with the trained model hosted externally due to size constraints.

## Instructions
1. **Set Up Environment**:
   - Open the notebook in Google Colab  with Python, PyTorch, OpenCV, and `gdown` installed.
   - Ensure an internet connection to download the model.
   - Install dependencies by running `pip install -r requirements.txt` before executing the notebooks.

2. **Download the Model**:
   - The trained model (`unet_model.pth`) is hosted on Google Drive due to its size (>25MB).
   - Run `inference.ipynb` directly. The first cell contains the Google Drive download link:
     ```python
     import gdown

     # Download model from Google Drive
     url = 'https://drive.google.com/file/d/1pjKT-Zxa-9kTlmKN5d0DjdLMvOcX72NM/view?usp=sharing'  
     output = 'unet_model.pth'
     gdown.download(url, output, quiet=False)

   **** Run Inference:****

After the model is downloaded, continue running inference.ipynb.
Upload a polygon outline image (e.g., diamond.png) when prompted.
Optionally upload a ground truth image (pre-colored polygon) for comparison.
Choose a color from the available options (cyan, purple, magenta, green, red, yellow, blue, orange).
The notebook will display the input polygon, mask, and colored output.


**Dataset:**

A dataset ZIP file is included in the repository. Extract it to access the training data (e.g., data.json and associated images). Ensure it’s uploaded to Colab or your local environment before training.

**wandb Link**

Training metrics and validation results can be viewed at: https://wandb.ai/charithareddyadoori-getayna/ayna-ml-assignment/runs/hizq6983



**Observations**

Initial inference had background color issues, which were resolved by using a mask derived from input contours.
Validation loss during training was below 0.1, indicating good model convergence.
The model was trained for 100 epochs with wandb logging for tracking.
**Files**

**inference.ipynb**: The main notebook containing the full pipeline (training, model download, and inference).
**download_model.ipynb**: A separate notebook to download unet_model.pth from Google Drive.
[dataset.zip]: Contains the training dataset (extract before use).
**README.md**: This file.
**requirements.txt**: Lists the required Python packages and versions.

**Notes**

The Google Drive link for unet_model.pth should be updated in inference.ipynb with the correct file ID.
Ensure gdown is installed (!pip install gdown if needed) to download the model.
Sample polygon images can be used for testing (e.g., upload your own or extract from the dataset ZIP).
