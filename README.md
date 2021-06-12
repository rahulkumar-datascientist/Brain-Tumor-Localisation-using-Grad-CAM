# Brain-Tumor-Localisation-using-Grad-CAM

## Part 1: Preparing the Dataset for Image Classification

### BRAIN TUMOR prediction using MRI Scans

BACKGROUND - Brain Tumors are complex. There are lot of abnormalities - Tumors can exist in various sizes and can be located in any part of the brain. This makes it really difficult to completely understand the nature of the tumor. The best technique to detect brain tumors is - Magnetic Resonance Imaging (MRI). A huge amount of image data is generated through these scans. These images are examined by radiologists to determine the next course of action.

### Dataset collection and description

- The Dataset of Brain MRI scans was downloaded from: https://www.kaggle.com/ahmedhamada0/brain-tumor-detection
- The dataset contains 3 folders/ Image classes: YES (Tumor is present), NO(Tumor is absent) and PRED(mix of both image classes) which contains 3060 Brain MRI Images. (1500 each for YES and NO class, 60 for PRED class)
- Each of the image are reshaped to size (224, 224) before training the CNN model (Present in SECTION - 2).

### Preparing the dataset for CNN model

- The dataset downloaded from the above mentioned link was downloaded as "archive.zip" file.
- Uploaded the zip file on google collab.
- Extracted the file as saved it in "MRI_dataset" folder. The folder contained 3 subfolders - YES, NO, and PRED - containing their respective images.
- Deleted the PRED folder as we only required 2 set of image classes.
- Used basic file operations to prepare the dataset in image_generator format - i.e., created TRAIN, VALIDATION and TEST folders with 70%, 20% and 10% of the images from YES and NO classes.

