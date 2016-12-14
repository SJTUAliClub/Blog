
# **A Brief Description on  CNN**
----

## **Introduction**
----

This article is a brief description of CNN which is one of the most popular convolution neural network using in graphics processing and learning. In this part I won't tell you a lot about the compulation of ceural network and I presume that you have known the basic knowledge of artificial neural network. If you find it hard to understand the conept, you'd better learn the neural network first. 

-----

### **The idea of Convolution**

----

Different from the tradition neural network, convolution ceural network is created to deal with the graphics based problem like object detection. In ANN, the fully connected network has too much parameters so the basic idead of CNN is to decrease the parameters using convolution. The different layers will be just partially connected. For instance, in the following picture we can see how the layer in m-1 will be connected the layer in m.



![layer](http://www.eamonalbert.com/static/img/blog/CNN/1.jpg "layer")

Besied, CNN can share the weights.



![layer](http://www.eamonalbert.com/static/img/blog/CNN/2.jpg  "layer")


In the picture, the lines with the same color means that they share the same weights. From layer m-1 to layer m, we use the convolution operation which means they have the same kernel.

The advantage of sharing the same weights is obvious, because it largely decrease the number of parameter and the number will stay the same no matter how large the number of neuron is.


![layer](http://www.eamonalbert.com/static/img/blog/CNN/3.jpg  "layer")


I use the graph above to show that the concept of kernel. One kernel can  extract one feature in the picture. Using multiple kernels, we can get multiple features and these features will be regarded as feature maps. For instance, we can use 100 kernels to get 100 features maps in one picture. So these features will be the neurons in this layer. The parameter in this layer will be number of kernel * the weights shared by each kernel.


The number of the neuron in hidden layer is decided by the raw image and the kernel size and the stride.

Later we will discuss the calculation of the neuron number in each layer.

-----

### **Analysising each layer**

----

![layer](http://www.eamonalbert.com/static/img/blog/CNN/4.jpg  "layer")

We discuss the CNN which is shown in the image above.

- First we input an image of 32x32

- After the input will come the hidden layer with 6 kernel and each kernel will produce 28x28 neurons. The kernel size if 5x5. So we can know the stride should be 1(because 32-28+1=5).


  Parameter number：（5×5+1）*6=156 （need one bias）

  Connected number： 156×（28*28）=122304

- Next comes the subsampling. It has 6 feature maps and each map has 14x14 neurons and kernel size is 2x2. Stride is 2. The function is to take half of the input image


  Parameter number： （1+1）*6=12

  Connected number： 14*14×(4+1)=5880

- C3 has 16 kernel and each feature map has 10x10 neurons and kernel size is 5x5. C3 connects the partial parameter in s2.


LeCun applys the following methos. 

  ![layer](http://www.eamonalbert.com/static/img/blog/CNN/5.png  "layer")

- S4 is subsampling

- C5 is convolution and has 120 feature maps. The kernel size if 5x5. Since the size of feature maps in S4 is also 5x5, the size of feature map in C5 will be 1x1. So C5 and S4 are fully connected.


  Parameter number：(5x5x16+1)x120=48120

  Connected number：48120x1x1=48120

- **FC6 is fully connection layer**

  Parameter number： （120+1)x84=10164

   Connected number：10164
   
   
-----

### **Contect Info:565953583@qq.com**

----




