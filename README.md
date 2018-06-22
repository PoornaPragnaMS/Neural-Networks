# Neural-Networks

In this project, we are going to construct an Artificial Neural Netwrok Model for geodemographic segmentation using Keras with Tensor Flow as a backend

## Requirements
Python 3.6

Keras = 2.x (Tensorflow backend)


## Data Preprocessing

First before we get into the NN Model, we will preprocess the data set to suite the requirement of Machine Learning Model. To do this, we are going to apply two techniques:

Standardization : Here we convert the categorical data to numeric values, for which we are using One Hot Encoder Technique
Normalization : Here we scale the data so that there are no inputs that dominate each other, we use standard scaling technique to keep the mean around zero and variance between 1 and -1

## Preparing the ANN model using keras with Tensor Flow as backend 

  Step 1: Initialize the random weights of smaller scale to the input data set
  
  Step 2: Place the observation data with each feature as one input node of the Neural Network
  
  Step 3: Using feed forward propogration technique(from left to right), activate the neurons such that the impact of activation is limited only by weights provided. Propogate the activations until getting the predicted result
  
  Step 4: Compare the predicted result with actual and measure the error
  
  Step 5: Use back propogration technique (from right to left) to propograte the error and update the weights according to how much they are responsible for.
  
  Step 6: Repeat the above step after each observation (stochastic gradient descent) or after batch of observation (batch gradient descent) 
  
  Step 7: Once the whole training data set is passed through ANN, it makes an epoch. Redo more epochs till we see the best result
  
  In ANN, we use hidden layers after the input layer and number of nodes in hidden layer is by experiment suggested to be of average of number of input and output nodes.Here we are choosing Rectifier as the activation function for neurons in hidden layers and Sigmoid function for output nodes.
  Again we can choose ensemeble technique to choose the number of nodes in hidden layers if we dont agree with experimented result
 
 For the back propogation technique we are using a  gradient descent  technique (algorithm used here for optimization is termed as Adam) with loss function being binary_cross entropy as our output values are binary classifier, here we are considering mini-batch gradient descent methodology which is a median of stochastic and batch gradient descent with batch size of 10 and epoch of 100.
 
 To increase the accuracy, we are using k-fold validation technique to achieve low bias and low variance and grid search technique for hyper parameter tunning to get the best suite parameters.
 
 ## Results
 
 With the first run after building the model, acurray was around 80~82%, with k-fold validaiton and grid search, accuracy increased to 82%


