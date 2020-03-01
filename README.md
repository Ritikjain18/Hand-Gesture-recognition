# mnist-handwritten-digits
MNIST dataset is one of the most common datasets used for image classification and accessible from many different sources. In fact even Tensorflow 
and keras allow us to import and download the mnist dataset directly from their API.

In MNIST datset, there are a total of 60,000 train and 10,000 test data.In order to identify handwritten digits , the concept of neural network is used.
Each image is 28x28 pixel square(784 pixel total). A standard split of the dataset is used to evaluate and comapare models,
where 60,000 images are used to train a model and a separate set of 10,000 images are used to test it.
It is a digit recognition task.As such there are 10 digits(0 to 9) or 10 classes to predict.

We will build our model by using high level Keras API which uses either Tensorflow or Theano on the backened. Therefore we will import 
the sequential model from keras and add Conv2D,MaxPooling,Flatten,Dropoutand Dense Layer. When it comes to images, 
there seems to be little correlation or relation between two individual pixel values unless they are close to each other.
This leads to the idea of convolution layers and Pooling layers.

Layers in CNN-
We are capable of using many different layers in a convolution neural network. However convolution, pooling and fully connected layers are the most important ones.

Convolution Layers-Convolution layers is the very first layer where we extract features from the image in out dataset. Due to the fact that pixels are only related with the adjacent 
and close pixels, convolution allows us to preserve the relationship b/w different parts of the image. Convolution is basically filtering the image with a smaller pixel filter to decrease the size of the image without losing the relationship b/w pixels.

Pooling Layers- When constructing CNNs, it is common to insert the pooling layers after each convolution layer to reduce the spatial size of the representation to reduce the parameter counts which reduces the computational complexity.
In addition, pooling layers also helps with the overfitting problem.

A set of Fully Connected Layers- A set of fully connected layer is our RegularNet where each parameter is linked to one another to determine the true 
relation and effect of each parameter on the labels. Since our time complexity is vastly reduced thanks to convolution and pooling layers , we can construct a fully 
connected network in the end to classify our images.
In addition dropout layers fight with the overfitting by disregarding some of the neurons while training while Flatten layers flatten 2D arrays 
to 1D array before building the fully connected layers.

After that I have separated these two groups as train and test and also separated the labels and images. X_train and X_test contain greyscale RGB codes
(from 0 to 255) while Y_train and Y_test parts contain labels from 0 to 9 which represents which no. they actually are.
To visualize these numbers we can get help from matpltlib.

We must normalize our data as it is always required in neural network models. We can achieve this by dividing the RGB codes to 255.

We also need to know the shape of the datset to channel it to the CNN. You will get (60,000 , 28, 28). As you might have guessed 60,000 represent 
the no. of images in the train datset and (28,28) represents the size of image 28x28 pixel.

We may experiment with any no. for the first Dense layer, however the final Dense layer must have 10 neurons since we have 10 classes (0-9)
You may always experiment with the kernel size, pool size, activation function, dropout layer to get better result.

