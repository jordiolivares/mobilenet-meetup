% From Dumbphone to Smartphone: How to run Computer Vision on anything
% Jordi Olivares
% March 12, 2020

# What is this talk about

## The problem

We want to run AI

# Mobilenet V1

## The core teaching

* We can factor convolution into applying a filter and combining the features
* We will call this Depthwise Separable Convolution

## Depthwise Separable Convolution

* A 2D filter is applied to each channel separately (M channels)
* The resulting feature map is convolved with N 1x1 convolutions

### An image is better

![Depthwise Separable Convolution 1](./dep_sep_conv_part_1.png)

![Depthwise Separable Convolution 1](./dep_sep_conv_part_2.png)

### Reduction in operations (w.r.t. normal Convolution)

![MAdds](./madds.png)

### Empirically it works almost the same

| Neural Net    | Accuracy | Million MAdds | Million Parameters |
| ------------- | -------- | ------------- | ------------------ |
| MobileNet-224 | 70.6%    | 569           | 4.2                |
| GoogleNet     | 69.8%    | 1550          | 6.8                |
| VGG-16        | 71.5%    | 15300         | 138                |

# Mobilenet V2

* Builds upon the Depthwise Separable Convolution
* Ingest new concepts such as Residual Networks (Resnet) and bottleneck layers
* Puts a new spin on them by creating the Inverted Residual Bottleneck layer

## Let's talk about information loss

![Information Loss](./information_loss.png)

## Inverted Residual Bottleneck Layers

### What's an Inverted Bottleneck layer?

![Bottleneck Layer](./bottleneck.png)

### What's an **Inverted** Residual Bottleneck layer?

![Inverted Residual Bottleneck](./inverted_residual.png)

### Give me the data, I don't care about your theoretics

![Inverted residual bottleneck block structure](./inverted_residual_bottleneck_layer.png)