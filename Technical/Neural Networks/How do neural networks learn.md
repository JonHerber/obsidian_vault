#ANN/gradientDescent/costFunction
# Defining "success"

The first thing we have to think about is: "How do we determine success for an ANN?"
Let's go back to our base-example of image recognition for hand-written digits. Success is obvious here: A **correct classification** means **success**, a **wrong classification** means **failure**.
Now think about it mathematically: How do we measure the difference between the actual classification and the predicted one?
This can be done, by defining a [[Cost function]]. We now calculate the average of this cost function across all of our training data:

![[Pasted image 20250328100818.png]]
In this example we use the sum of squared differences as a cost function.

# Initializing an ANN

Since the network has to start somewhere, we take the easiest approach: We **randomize** all the weights and biases in the beginning. This of course yields a horrible prediction result for any of our data, since it has not actually learned anything yet.

# What is learning

Since our success is - mathematically speaking - a minimal value for our loss function, we have the goal of minimizing this loss function. This can be done by calculus. 
Let's imagine a function with **only one parameter**. We now want to find the minimum for this function:

![[Pasted image 20250328102243.png]]

We start at the yellow dot, and our goal is to find the local minimum. For this we can use the mathematical gradient. It describes the steepest gradient in the area. Since we want to find the minimum, we want to use **gradient descent**.
If we add another parameter (and therefore an additional dimension), it looks like this:
- [ ] Learn about gradient descent

![[Pasted image 20250328102535.png]]

The x and z axis would be the parameters and the y-axis is the value of our cost function.
For our example with the digit recognition we have ~13k parameters --> 13k dimenstions!

What our gradient descent gives us for each iteration step, is a "direction" we should move to:
![[Pasted image 20250328102835.png]]
This means, that some parameters are **more important** for our task than others, since they have a higher magnitude of changing. 

Note: I mentioned, that the ANN does not actually split the task into the subproblems as we did, but if we visualize, what the first hidden layer looks like instead it is this:
![[Pasted image 20250328103103.png]]
These are the visualized weights of the first layer to the second layer. 

*Note:* If we input an image with only noise, we might expect, that we would get an ambiguous result, or no result at all, however since the ANN is seeing the world only through the glasses of "minimizing a loss function" it will actually give a clear result, which is just rubbish. 
![[Pasted image 20250328103535.png]]

*Additional Note* : Researchers have found out, that ANNs not only "memorize the labels" but actually learn to see patterns. This could be proven by taking a labeled data set, and shuffling the labels. After the training the ANN could predict the values for the training data quite accurate, but not for new data points. This is to be expected since it was fed "wrong information". However the interesting part is the comparison of the comparison of the values of the cost function for the proper annotated data vs wrong labeled one:
![[Pasted image 20250328104014.png]]

It can be seen, that the model "learns" (minimizes) at a much higher rate, especially in the beginning   
