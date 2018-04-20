# A-simple-explanation-of-Neural-Networks

        
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

**Layers in a Neural Network**
Each connection from one unit to another will have its own assigned weight which is generally a number between zero and one. Weights represent the strength of the connections between the units. First when we receive a input at the input layer that input is passed to the neuron in the next layer via a connection and the input is multiplied by the weight assigned to this particular connection. A weighted sum is then computed with each of the connections that are pointing to this neuron. The sum is then passed to an activation function which transforms the result into a number between 0 and 1. Once we get the result of the transformation from the activation function, that result is passed on to the next neuron in the next layer. The same process which we described now from receiving the input at each layer to the transformation by an activation function occurs over and over again until we reach the output layer. Also during this process, the weights for each connection will continuously be changing in order to reach optimized weights for each connection as the model continues to learn from the data.
We reach the output layer following the hidden layer. We have two output units/neurons in this layer; these units typically represent categories (of data).
For eg., if this model has a task of classifying if this image is an image of a cat or a dog, then the output layer would have two 
units representing two possible outputs cats and dogs. If we add image of another animal say parrot, and we want our model to classify our image based being it of a cat or dog or parrot, as such our output layer will have three units representing each of the three possible image types.

This is how layers in a neural network function in general.


    

