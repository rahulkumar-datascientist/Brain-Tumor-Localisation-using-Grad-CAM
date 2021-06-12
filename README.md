# Brain Tumor Localisation using Gradient Weighted Class Activation Mapping (Grad-CAM)

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

## Part 2: Creating Base Model

### Data Pre-processing
Using ImageDataGenerator to create batches of of tensor image data with real-time data augmentation such as

- Rotating the image by 10 Degres on its axis
- zooming on the image by 15%
- flipping the image horizontally as left and right lobe has same area - This would simulate more images for training and detecting tumor on either side of the lobe.

## Part 3: Neurons Correlation with Class label
To Identify neurons which are strongly correlated with the class label

- Identify the last layer/ output layer of the model.
- Create a feature extractor model where the model accepts the input and returns the output from the last layer of the base model(identified above).
- Pass a batch of images to the newly created feature extractor model to find the output tensor of shape (None, 5, 5, 2048).
- Pass the output tensor throuh a Global average pooling layer to downsample the data.
- Finally pass the output from above to a softmax function to get the neurons value between [0-1].
- Convert the resultant to a numpy array of shape(no_of_images, number_of_neurons).

## Part 4: Object Localisation using GRAD-CAM
By using a global average pooling (GAP) layer at the end of a neural network instead of a fully-connected layer, we get excellent localization, this gives us an idea about where neural network pay attention.

Reference: http://cnnlocalization.csail.mit.edu/Zhou_Learning_Deep_Features_CVPR_2016_paper.pdf