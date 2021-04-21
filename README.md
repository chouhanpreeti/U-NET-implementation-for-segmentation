# U-NET-implementation-for-segmentation
A simple UNET Implementation for pixel level classification of images with VGG19 Encoder.



About the Dataset:
This dataset contains brain MR images together with corresponding segmentation masks.
The images were obtained from The Cancer Imaging Archive (TCIA).
Tumor genomic clusters and patient data is provided in data.csv file.

Get Data from here:https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation/metadata


Objective:

The main agenda is to perform the Semantic Segmentation Of MRI Scans based on training data. The data contain an image along with the predicted mask from a radiologist showing the area suspected for the tumor in the brain (localization of the tumor in the images). - This is attained by a UNET model. 

All the files are read from the directory and saved as image_path, mask_path, and Patient ID into pandas dataframe for further processing. Visualisation and dropping of duplicate values is also done to avoid errors. 


This diagram below gives us an idea of what UNET model is and how it basically works.  
![UNET_model](https://github.com/itspreeti25/U-NET-implementation-for-segmentation/blob/main/unetmodel.png)


Research Paper Followed:https://arxiv.org/abs/1505.04597

