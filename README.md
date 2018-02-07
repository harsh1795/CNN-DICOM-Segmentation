# HealthCare
**Project : Image Segmentation of Dicom Images to remove headrest label from head CT scans**
Please give a :star: if you like my work.:smiley:
**Description**
 - Programming Language - **Python2, Jupyter, Tensorflow**
 - Task: Remove Headrest from all the scans of patient given in dicom format using **Convolutional Neural Networks by Image Segmentation**
 
**Data Preprocessing**
 - Reading Dicom Images from **pydicom** package and store image in numpy arrays.
 - converting raw grayscaled images stored in Hounsfield Units into meaningful numpy arrays for CNNs by rescaling them using slope and threshold from dicom image header.
 - Creating GroundTruth Labels by segmenting images using K-Means and finding non-connected components to identify headrest label. Finally segmenting them by mean and standard deviation of HU units.
 - Storing these labels as segmented labels for training input images.
 
**Building CNNs**
 - Input Image - 512 * 512 greyscaled images
 - Output - Segmented label for Headrest 
 - Build different models:
   - 3 Layer - 2 Convolutional/Deconvolutional in each layer - 2 Max pooling - "VALID" padding (size not same of output)
   - 7 Layer - 2 Convolutional/Deconvolutional (First 3 layers), 4 (Next 3 layers), 8(Last layer) - 6 pooling and upsampling layers - "SAME" padding
 - Performing much better than thresholding methods
 
**Results & Visualization**
 - Achieved accuracy above **99%** in Image segmentation of 500 dicom images.
 - Images are uploaded in **model_12_hr_250_50 >> prediction** of validation images per epoc. 
   
