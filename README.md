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



Why create a custom data generator and zip images and masks together in this case?

For segmentation or pixel level classification where we have an image and a corresponding mask localizing the object (or in this case a tumour), we need a new function that will generate both the training image and corresponding mask that we will use to feed into the fit_generator method. Specifically, the way fit_generator works is that yields a sequence of tuples such that the first element of the tuple is the image and the second element is the expected output. By simply using the data generator on its own, the sub-directories will implicitly encode the expected label of the image. This is of course no longer the case when you're trying to do semantic segmentation.
Basically the function takes two ImageDataGenerators and zip them together, then have a loop that will yield each batch of training images and expected output labels.



This diagram below gives us an idea of what UNET model is and how it basically works.  
![UNET_model](https://github.com/itspreeti25/U-NET-implementation-for-segmentation/blob/main/unetmodel.png)


Research Paper Followed:https://arxiv.org/abs/1505.04597

