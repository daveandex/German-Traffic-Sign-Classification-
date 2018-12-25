# Traffic sign classification using CNN
Classification of German traffic signs using convolutional neural network. This is a basic algorithm with a simple data preprocessing but without data augmentation and hyperparameter tuning. Implementation using keras and tensorflow.   

The model achieved a test accuracy of **97.9%**. 

## The Dataset

The [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset) consists of about 50,000 trafic sign images of 43 classes. The images are 32×32×3 array of pixel intensities. The pickeled images can be download from from [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/5898cd6f_traffic-signs-data/traffic-signs-data.zip). 

## Preprocessing

The images were converted to grayscale, i.e., only a single channel will be used (Pierre Sermanet and Yann LeCun showed that using all the channels will not lead to any improvement, [read the paper here](http://yann.lecun.com/exdb/publis/pdf/sermanet-ijcnn-11.pdf). Since, the dataset was collected from real scenarios under different lighting conditions,  the images have variable brightness and contrast. Hence, local histogram equalization was also applied. 

## Model Architecture

An architecture similar to [VGG](https://arxiv.org/pdf/1409.1556.pdf)[SZ14].

A fairly simple archtecture with 4 convolutional layers and 2 fully connected layers was used. 

Here are the steps:

Input => Convolution => ReLU => Convolution => ReLU => Pooling => Convolution => ReLU => Convolution => ReLU => Pooling => FullyConnected => ReLU => FullyConnected => ReLU => Output

### Regularization
To minimize overfitting, dropout was added on the fully connected layers and on two of the conv layers. 

## To further improve the prediction accuracy

* Data Augmentation and class balancing
* Further preprocessing
* fine-tuning

 
