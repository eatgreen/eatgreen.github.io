# Pytorch 
In PyTorch you define your Models as subclasses of torch.nn.Module.

In the __init__ function, you are supposed to initialize the layers you want to use. Unlike keras, Pytorch goes more low level and you have to specify the sizes of your network so that everything matches.

In the forward method, you specify the connections of your layers. This means that you will use the layers you already initialized, in order to re-use the same layer for each forward pass of data you make.

torch.nn.Functional contains some useful functions like activation functions a convolution operations you can use. However, these are not full layers so if you want to specify a layer of any kind you should use torch.nn.Module.

You would use the torch.nn.Functional conv operations to define a custom layer for example with a convolution operation, but not to define a standard convolution layer.

## Convolution
The command torch::nn::Conv2d 

- is able to construct a convolutional operator. It accepts two channel number, input channel corresponds to the image data that you have. For gray image it is 1. The output channel corresponds to the features that you want to extract. Say it is et to be 5, that means you are extracting 5 feature channels from the raw image.  
- Say we set 1 input channel and 5 output channels, then the size of your CNN needs to be adapted as well.

## Max Pooling
The command torch::nn::MaxPool2d(kernel_size, stride, padding) 

- Reduce size of the feature map

## ReLU, Rectified Liner Unit
The command torch::nn::relu(x) 

- ReLU(x)=max(0,x)


## Fully Connected Layers/Linear layers
The command torch::nn::Linear(in_features, out_features)

- $y=xA^T + b: A \in R^{infeatures \times outfeatures}$

## Dropout