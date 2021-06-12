# Brain-Tumor-Localisation-using-Grad-CAM

## Part 1: Preparing the Dataset for Image Classification

### BRAIN TUMOR prediction using MRI Scans

BACKGROUND - Brain Tumors are complex. There are lot of abnormalities - Tumors can exist in various sizes and can be located in any part of the brain. This makes it really difficult to completely understand the nature of the tumor. The best technique to detect brain tumors is - Magnetic Resonance Imaging (MRI). A huge amount of image data is generated through these scans. These images are examined by radiologists to determine the next course of action.

### Dataset collection and description

- The Dataset of Brain MRI scans was downloaded from: https://www.kaggle.com/ahmedhamada0/brain-tumor-detection
- The dataset contains 3 folders/ Image classes: YES (Tumor is present), NO(Tumor is absent) and PRED(mix of both image classes) which contains 3060 Brain MRI Images. (1500 each for YES and NO class, 60 for PRED class)
- Each of the image are reshaped to size (224, 224) before training the CNN model (Present in SECTION - 2).
