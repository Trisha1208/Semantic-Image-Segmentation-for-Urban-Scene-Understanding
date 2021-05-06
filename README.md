# Semantic-Image-Segmentation-for-Urban-Scene-Understanding
FCN with Resnet50 Encoder using Transfer Learning

# Semantic Image Segmentation
Label each pixel of an image with a corresponding class of what is being represented referred to as dense prediction. 
Fine-grained inference by making dense predictions inferring labels for every pixel, so that each pixel is labeled with the class of its enclosing object or region.

![Image Segmentation](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.kaggle.com%2Fdansbecker%2Fcityscapes-image-pairs&psig=AOvVaw0M5_bOePgq9tIGTNcrcq8v&ust=1620397018613000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCPDLsZugtfACFQAAAAAdAAAAABAD)

This dataset is taken from Kaggle and mainly focuses on semantic understanding of urban street scenes.
Cityscapes Image Pairs dataset is a processed version of the original Cityscapes dataset which contains labelled videos.
The dataset has still images from the original videos, and semantic segmentation labels are shown in images right alongside the original image 2975 training images files and 500 validation images.
Dimension of each image is: 256x512 pixels.
Link:https://www.kaggle.com/dansbecker/cityscapes-image-pairs

## Transposed Convolution  
* Transposed Convolution or like some people incorrectly call it Deconvolution, can be seen as an opposite action to Convolution. 
* Unlike convolution, a transposed convolution layer is used to upsample the reduced resolution feature back to its original resolution. 
* A set of stride and padding values is learned to obtain the final output from the lower resolution features. 

## Skip Connections 
* Downsampling reduces the resolution of the input by a large factor, thus during upsampling it becomes very difficult to reproduce the finer details even after using sophisticated techniques like Transpose Convolution. 
* Obtain a coarse output.
* Adding ‘skip connections’ in the Upsampling stage from earlier layers and summing the two feature maps. 
* These skip connections provide enough information to later layers to generate accurate segmentation boundaries.This combination of fine and coarse layers leads to local predictions with nearly accurate global (spatial) structure. 
![skip connections]()

# Implementation Details

* Classify each pixel of the image into a particular class.
* CNN used for classification takes an image as input.
* Series of convolutional and pooling layers. 
* Uses fully-connected layers in the end to output a fixed length vector.
* The fully-connected layers at the end are replaced by convolutional layers.
* Output will be with coarse spatial features, which can be further upsampled to form the classification maps corresponding to our image.
* Three different methods implemented:
## U-Net
![U-Net]()
## Fully Convolutional Network with VGG16 encoder
![VGG16]()
## Fully Convolutional Network with ResNet50 encoder
![ResNet50]()
