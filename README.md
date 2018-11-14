# A-simple-explanation-of-Neural-Networks
This article is just to give a glimpse or a basic understanding of how the neural networks work in general. The different topics discussed here can be referred for more advanced explanations.
        
**Machine Learning**

Machine Learning is a practice of using algorithms to analyze data, learn from that data and then make predictions about new data.
With machine learning, rather than manually writing code to accomplish a set of instructions, the machine is trained using lot of
data and algorithms that gives the ability to perform the task without being explicitly being told how to do so.



**Deep Learning**

Deep Learning is a sub field of machine learning that is inspired by the structure and function of brain's neural networks. The
algorithms and models in deep learning are based on the structure and function of the brain's neural networks and its learning occurs     either in supervised or unsupervised form.



**Supervised and Unsupervised learning**

Supervised learning basically occurs when our deep learning model learns and makes inferences from the data that has been already 
been labeled. Unsupervised learning, however, occurs when the model learns and makes inferences from unlabeled data.



**Artificial Neural Networks**

The models in Deep Learning are called Artificial Neural Networks. The terms model, net, neural net, artificial neural network are generally used interchangeably in the deep learning field.

Artificial Neural Networks are computing systems that are inspired by the brain's neural networks. Artificial Neural Networks are 
based on a collection of connected units called neurons or nodes. The connection between these neurons can transmit a signal from 
one neuron to the other and then the receiving neuron then processes the signal and then signals downstream neurons connected to it. 
Typically neurons are organized in layers. Different layers may perform different kinds of functions or transformations on their 
inputs and signal essentially travels from the first layer called the input layer to the last layer called the output layer. Any 
layers between the input and output layers are called hidden layers.

Some commonly used layers are Dense or fully connected layers, Convolutional layers, Pooling layers, Recurrent layers, Normalization layers, many others.

For example, a convolutional layer will likely be used in a model that is doing work with image data. A recurrent layer will be used 
in a model that will work with time series data. A dense layer is just a layer that connects each input to each output within its 
layer.


   ![neural networks](https://user-images.githubusercontent.com/32324416/39083687-13d29b14-4586-11e8-8ac4-4601c00fb6a9.png)


**Layers in a Neural Network**

Each connection from one unit to another will have its own assigned weight which is generally a number between zero and one. Weights represent the strength of the connections between the units. First when we receive a input at the input layer that input is passed to the neuron in the next layer via a connection and the input is multiplied by the weight assigned to this particular connection. A weighted sum is then computed with each of the connections that are pointing to this neuron. The sum is then passed to an activation function which transforms the result into a number between 0 and 1. Once we get the result of the transformation from the activation function, that result is passed on to the next neuron in the next layer. The same process which we described now from receiving the input at each layer to the transformation by an activation function occurs over and over again until we reach the output layer. Also during this process, the weights for each connection will continuously be changing in order to reach optimized weights for each connection as the model continues to learn from the data.
We reach the output layer following the hidden layer. We have two output units/neurons in this layer; these units typically represent categories (of data).
For eg., if this model has a task of classifying if this image is an image of a cat or a dog, then the output layer would have two 
units representing two possible outputs cats and dogs. If we add image of another animal say parrot, and we want our model to classify our image based being it of a cat or dog or parrot, as such our output layer will have three units representing each of the three possible image types.

Just to add, the value of weights can be negative too. Also the output of the activation function can be negative if Tanh is used as an activation function to transform the result.

This is how layers in a neural network function in general.


   ![nn_weights 2](https://user-images.githubusercontent.com/32324416/39083693-2670514e-4586-11e8-9dca-e53c0e1a347d.png)


**Activation Functions**

An activation function typically follows a layer or we say that it is a part of the layer. In artificial neural network, the 
activation function defines the output of a neuron given a set of inputs.

               output = activation(weighted sum of inputs) connected to that neuron.

The activation function performs some types of operation to transform that weighted sum a num between a lower limit and a upper 
limit. To understand why we need activation function, an activation function is biologically inspired by the activity in our brain 
where different neurons fire or are activated by different stimuli. 

There are different types of activation functions used in neural networks and different activation functions can be used in different layers.


**Sigmoid** - If the input is a very negative number then the sigmoid will transform the input to a num very close to zero. If the 
input is a very positive number, the sigmoid will transform the input to a num close to 1. If the input is zero, the sigmoid will transform it to a num b/w zero and one. in case of sigmoid, 
0 is the lower limit and 1 is the upper limit. A neuron can be between 0 and 1. So the closer to 1, the more activated that neuron 
is. The neuron is less activated if it is closer to 0.

**Relu** - One of the most widely used activation functions today called relu (Rectified Linear Unit) transforms the input to the maximum of either 0 or the input itself. So if the input is less than 0, the relu will transform the input to be 0. If the num is greater than 0, the relu will just output the same output.  The more positive the neuron, the more activated it is.
 
 There are many different types of activation functions that do different types of transformations to the inputs.


**Before we dive more into understanding the training process, let get some idea of some terms used in neural networks.**


**Parameters** - Parameters are something that a model learns on its own, are internal to the model and whose value can be estimated from data. Some of the examples of parameters are weights, bias.

**Hyperparameters** - Hyper-parameters are things that we need to tell the model or learning algorithm. Some of the examples of 
hyperparameters are learning rate, number of hidden layers, number of hidden units, activation function etc. In other words, we can
say that the hyper-parameters are parameters which we specify externally and so they control the ultimate parameters (weights and bias)

**Loss Function** - A loss function is used to measure the inconsistencies between the predicted value and the actual label of the 
input data. Loss function tells us how quantitatively bad our predictions are as compared to our actual labels/target labels. It is a non-negative value where the robustness of the model increases along with the decrease of the value of loss function. A commonly used loss function is cross entropy. There are other types of loss function as well like hinge loss etc.

**Optimization Technique** - The optimization technique is designed to modify parameters in order to decrease the error/increase the accuracy in the next step ultimately maximizing the accuracy/minimizing the error. This is generally done using Gradient Descent algorithm.



**Training a Neural Network**

When we train a model, we are basically trying to solve an optimization problem. We are trying to optimize the weights within the model. We already mentioned that each connection has a weight assigned to it. During training, the weights will constantly be updated to reach their optimal values. The weights are optimized based on the optimization algorithm or optimizer that we choose to use for our model. Most widely used algorithm is called stochastic gradient descent or SGD. The objective of any optimization algorithm is to minimize a loss function. The SGD will be assigning the weights in such a way so as to make the loss as close to zero as possible. There are several loss functions, for example, mean squared error.

During training we supply our model with data and labels to that data. For e.g., we have a model that we want to train on classifying whether the images are of  a cats or dogs, then we supply the model with images of cats and dogs along with the labels for these images that tell whether the image is of a cat or a dog.

Let’s suppose after training, we pass an image of a cat through the network, the model will give an output at the end. The output is what the model thinks the image is either a cat or a dog. It actually consists of the probabilities for cat or dog. It may assign 75% probability to the image being a cat or 25% probability to the image being a dog. It assigns a higher likelihood of an image being a cat than a dog. In this case, the loss is the error between what the model is predicting for the image versus what the true label of the image actually is. Thus the optimization algorithm basically tries to minimize this error to make our model as accurate as possible in its predictions.

After passing in all of the data through the model, we continue to pass the same data over and over again. During this process of repeatedly sending the data into the model, is when the model will actually learn. During this process of optimization, the model will learn from that data and then update the weights in the model accordingly.



**How a Neural Network learns**

A single pass of the data through the network is called an epoch. The same data will be passed over and over again through multiple epochs and during this process, the model learns.
When the model is first initialized it is set with some arbitrary weights. Also at the end of the network, the model will give an
output for a given input. Then it will compute the loss or the error of that output by looking at what the model predicted versus 
the true label of the input. At this point the model will compute the gradient of the loss function with respect to each of the 
weights that have been set. Once we have the value of the gradient, this is multiplied by a learning rate. A learning rate is a 
small number usually ranging between 0.01 and 0.001. So any value we get of the gradient will become relatively small once it is multiplied with the learning rate. We then take this value and update the given weight with it, essentially removing the previous 
weight on the connection and update the weight on that connection with this new value. This process happens with each of the weights
in the model each time the data passes through it. This updating of the weights is essentially we say that the model is learning. 
It’s learning what values to assign to each weight based on how those incremental changes are affecting the loss function.

We now have a general idea about how to train the model and how the model learns through this training process.



**Train, Test & Validation Sets**

For training and testing purposes, the data is broken down into 3 distinct datasets. These datasets consists of a training set, validation set and a test set.

**Training Set** - It is a set of data that is used to train the model. During each epoch, the model will be trained over and over 
again on the same data in the training set and continue to learn about the features of this data. The help with this is that later
we can deploy our model and make it predict on data which it has never seen before. It will make predictions based on what it learns about the training data.

**Validation Set** - Validation set is a dataset that is separate from our test set which is used to validate our model during 
training. This validation may give us information that may help us adjusting the hyper parameters. With each epoch during training,
the model is trained on the data in the training set, it will also be simultaneously validating on the data in the validation set.
We know that during the training process, the model will be classifying the output for each input in the training set.
After this classification occurs, the loss is then calculated and the weights in the model are adjusted. Then during the next epoch,
it will classify the same input again. Also during training the model will be classifying from each input from the validation set as well. It will be doing this classification based only on what it has learned about the data its being trained on from the training 
set. The weights will then be updated in the model based on the loss calculated from our validation data. The data in the validation
set is separate from the data in the training set. So when the data is validating on this data in the validation set, this data does 
not consists of the same data that the model is already familiar with from training. The reason we need a validation set is to ensure that our model is not overfitting to the data in the training set. The idea of overfitting is that our model becomes really good at being able to classify the data in the training set but its unable to generalize and make accurate classification on the data that is was not trained on. During training it will also be validating the data in the training set and see if the results that it is giving 
for the validation set are just as good as the results it is giving for the training data.
If the results on the training data are really good but the results on the validation data are not good enough then the model is 
likely overfitting.

**Test Set** - The test set is a set of data that we use to test the model later the model has already been trained. This test set 
is separate from both the training set and the validation set. After the model is being trained and validated using the training and validation sets, we will then use our model to predict the output of the data in the test set. One major difference between the test 
set and the other two sets is that the test set should not be labeled. Training set and validation set have to be labeled so that we 
can see the metrics given during the training like the loss and the accuracy from each epoch. 
The model when predicts on unlabeled data in the test set, this is the same type of process that will be used if we were to deploy 
our model in the production field.



**Overfitting**

Overfitting occurs when our model becomes really good at being able to classify or predict on data that is included in the training
set but is not so good at classifying data that it was not trained on. So, essentially the model has overfit the data in the training set. We can find out if our model is overfitting based on the metrics that are given for our training and validation data during the training process.
When we specify validation set during training, we get metrics from the validation accuracy and loss as well as the training accuracy and loss. If the validation metrics are considerably worse than the training metrics, then that’s the indication that our model is overfitting. We can also get an idea that our model is overfitting if during training our model's metrics were good but when we use 
the model to predict on test data, is not accurately classifying the data in the test set. The concept of overfitting boils down to 
the fact that our model is unable to generalize well, meaning that it has learned the features of the training set extremely well 
that if we give the model any data that slightly deviates from exact data that is used during training, the model is unable to generalize and accurately predict the output. Overfitting is a common issue.



**Underfitting**

Underfitting is opposite to Overfitting. A model is said to be underfitting when it is not even able to classify the data that it was trained on well. We can tell that the model is underfitting with the metrics given for the training data are poor, meaning that the training accuracy of the model is low and/or the training loss is high. If the model is unable to properly classify the data it was trained on, is likely not going to do well on data that it has not seen before.



**Regularization**

In general regularization is a technique that helps reduce overfitting or reduce variance in our network by penalizing for complexity. The idea is that certain complexities in the model may make our model unlikely to generalize well even on the training data. Given 
this if we add regularization to our model, we are essentially trading in some of the ability to fit the data well for the ability 
to have the model generalize well for the data that is has not seen before. To implement generalization, is to simply add a term to 
our loss function that penalizes for large weights. The most common regularization technique is called L2 Regularization.

In other words, regularization is nothing but adding a penalty term to the objective function and control the model complexity using that penalty term. It penalizes the model rather than explicitly trying to fit the training data.



**Learning Rate**

The main purpose of the gradient descent is to minimize the loss between the actual output and the predicted output from our given training samples. We start the training process with arbitrarily set weights and then we incrementally update these weights as we move closer and closer to the minimized loss. The size of these steps that we are taking to reach the minimized loss is going to depend on learning rate.



**Batch Size**

Batch size is the number of samples that will be passed through to the network at one time('batch' aka 'mini-batch'). Recall that an epoch is one single pass o all the data through to the network. The batch size and epoch are not the same thing. Example - Let’s say
we have 1K images of dogs that we want to identify different breeds of dogs. Now let’s say we specify our batch size to be 10. This means that 10 images of dogs will be passed as group or as a batch at one time to the network. Given that a single epoch is one single pass of all the data through the network, it will take 100 batches to make up 1 full epoch.

                        1000 images / batch size of 10 = 100 batches per epoch.

Larger batch size will be equivalent to faster training. The tradeoff however is even if our machine can handle large batches; the quality of the model may degrade as we set our batches larger and may ultimately cause the model to be able to generalize well on 
the data that it has not seen before. Thus batch size is another hyperparameter that we may test and tune based on how our specific model is performing during training.   


That's all for now! Happy Learning !!

