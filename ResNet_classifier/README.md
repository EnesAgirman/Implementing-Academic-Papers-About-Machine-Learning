# ResNet Implementation

**ResNet**: ResNet (Residual Network) is a deep convolutional neural network (CNN) architecture
designed for image classification tasks. It was introduced in 2015 and is known for its deep network
structure, making it easier to train very deep neural networks without the problem of vanishing
gradients.

It was introduced in 2015 in the "Deep Residual Learning for Image Recognition" paper by Kaiming He, Xiangyu Zhang, Shaoqing Ren and Jian Sun. The ResNet paper can be obtained from the following link:

[https://proceedings.neurips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf ](https://arxiv.org/pdf/1512.03385.pdf?ref=blog.paperspace.com)

Note: I experimented on changing the activation functions on the AlexNet architecture from ReLU to Leaky ReLU functions which gave me better results.

## Dataset
Instead of implementing the alexnet architecture on the ImageNet dataset, I implemented the same neural network architecture 
on the microsoft cats and dogs dataset whiich can be obtained from the following link:

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
