# VGG Implementation

**VGG16**: VGG16 is a convolutional neural network (CNN) architecture designed for image classification
tasks. It was introduced in "VERY DEEP CONVOLUTIONAL NETWORKS FOR LARGE-SCALE IMAGE RECOGNITION" paper by Karen Simonyan and Andrew Zisserman.The paper can be obtained from the following link:

https://arxiv.org/pdf/1409.1556.pdf?ref=blog.paperspace.com

## Dataset
Instead of implementing the VGG architecture on the ImageNet dataset, I implemented the same neural network architecture 
on the microsoft cats and dogs dataset which can be obtained from the following link:

https://www.microsoft.com/en-us/download/details.aspx?id=54765

The dataset contains over 25.000 images of cats and dogs taken from animal shelters across United States 

## Data Preprocessing

1) We first unzip the data that is downloaded from the given link and placed at the same directory as the code
2) Iterate through the images in the unzipped dataset and divide them into train, validation and
test folders. Create a pandas dataframe for each of them and store the classes of the images as 0
or 1 in these dataframes
3) While saving the images into the train, validation, test folders, resize them into the proper size
you have decided to use
4) Opencv gives a Filenotfound error when trying to resize a corrupted image. Catch these errors
and delete the corrupted images.
5) Save the dataframes as .csv files
6) Create a dataset class as an extension of torch.utils.data.Dataset class. This class takes the image
and label directories and store the labels and the directory of each image their respective arrays.
We didn’t save the images but their directories because saving the images hold a lot of memory.
7) Create a getitem function that fetches the image from its directory, applies transformation if any
is given and return it along with its label.
