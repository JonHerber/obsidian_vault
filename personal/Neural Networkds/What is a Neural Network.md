#ANN 
# What is the structure of a neural network

A neural network (nn) is a sum of one Input Layer, some hidden layers and one output layer.
![[Pasted image 20250328080635.png]]
The above example shows an ANN with: 
- one input layer (784 neurons)
- two hidden layers (16 neurons each)
- one output layer (10 neurons)

## What does a neural network do

Can be used for any kind of prediction/classifying tasks. In the above example the ANN is used to recognize numbers from an image 

![[Pasted image 20250328081621.png]]

Let's stick to the above example: We have 784 input neurons, each holding a number between 0 and 1, representing the gray scale in each of the 28px x 28px image. 
We can now think about it that way. Each activation of different neurons lead to an activation of different connected neurons. (See above picture, where the green neurons are "activated").
To visualize it a bit more, let's break our task down a bit more.

### Breaking our task into smaller problems

If we see a digit, we can recognize, that it consists of different "sub-structures":
![[Pasted image 20250328082419.png]]
In this picture, we can see that a "9" for example consists of a loop in the upper part of the picture and a line in the middle/right part. An 8 e.g. consists of two loops etc.

Let's now think of it that way: Our output layer wants to represent all of our output possibilities (in our example all the numbers from 0-9). Our second to last layer wants to represent these above mentioned sub-structures, If we visualize this the ANN gets less "blackboxy" already:
![[Pasted image 20250328082809.png]]
We can now see, that e.g. the neurons in the last hidden layer are activated, that represent the "upper loop" and the "middle/right line". This leads to an acitvation of the output neuron that is mapped to a "9".

![[Pasted image 20250328083408.png]]

The first hidden layer could now represent even smaller subproblems of the "recognizing sub-patterns" problem. Just how we broke down our numbers into a combination of 16 sub-patterns, we can break those sub-patterns down into 16 sub-sub-patterns. Our input layer then represents All the possible pixels of an 28x28 image. Dependent on which pixels have which gray-scale different sub-sub-structures are visible. Different "sub-sub-structures" make different "sub-structures" and they make a final "digit". 

**Important note:** This is actually **NOT** what an ANN is actually "thinking", but much rather gives a really simple way of imagining it!

# How can a network be represented

As mentioned an ANN is just a sum of neurons, weights and biases. We can represent this by a matrix that consists of the weights (w), the value of the incoming neurons (a) and the biases (b): 
![[Pasted image 20250328092600.png]]
This would be the matrix to compute one layer. A whole ANN would be a sum of such matrices.
Note: More explanation here: [[Neurons]]

In our case we would have ~13k adjustable parameters:
![[Pasted image 20250328093015.png]]


