#ANN 
# What is a Neuron

Think of a neuron as a node in a graph, that (usually) has multiple incoming edges from different nodes and (usually) multiple outgoing edges to different other neurons. These edges are the connection of the layers before and after the current layer the neuron sits in. 

A neuron (usually) holds a value between 0 and 1, whereas it is considered activated once it passes a certain threshold. 

# How do neurons activate

A neuron gets activated based on its predecessors. All the (connected) neurons from the predecessing layer have an influence of wether a neuron is activated or not. For example for an input layer with 784 neurons the first hidden layer could look like this:
![[Pasted image 20250328084631.png]]
Now the question rises: **What should our neuron represent**: 
Let's say we are in the digit recognition example, and we are in the first hidden layer. Maybe we want our neuron to activate, if a pattern that represents a vertical line in the top part of our image is present. 
![[Pasted image 20250328085000.png]]
We would then want, that these (and maybe some around that area) are activated, in order to recognize this pattern. This would mean, that if those pixels are present (which means that these neurons in the input layer are activated), we want our neuron to activate. 

This can be achieved through the "edges", which are called weights. If a neuron of the layer before this one is considered to be important for this one to be active, we want it to have a **positive weight** otherwise we want it to have no weight or maybe even a **negative weight** if it would mean, that a certain sub-pattern is probably not present. 
If we visualize this, it could look like this:
![[Pasted image 20250328085518.png]]
Our neuron value can be represented as the sum of all connected neurons multiplied by their corresponding weight:
![[Pasted image 20250328085623.png]]
If we represent these weights as a small image aswell, it get's more clear: Let's say a green pixel means a positive weight (and therefore correlation) and a red pixel means a negative weight (and therefore correlation) to this specific neuron. Again, I want you to think about the fact, that we want to recognize the pattern of a vertical line in the top part of our image. 
![[Pasted image 20250328085908.png]]
# How to "normalize" the activation

Since we want our neuron to hold a value between 0 and 1 we need some kind of "fitting" function for the sum, that is shown above. For this we can use an [[activation function]] . A standard for this would be the **sigmoid function**:

![[Pasted image 20250328090224.png]]

This makes sure, that all the negative values end up close to 0 and all positive values end up close to 1, whilst never leaving this are. 
Let's modify our above seen sum to calculate our neuron activation accordingly:
![[Pasted image 20250328090412.png]]

# Biases

What if we want to really make sure, to be extremely accurate when picking up a signal? In this case we could introduce a **bias**, that **raises the threshold** for activation of that specific neuron. This can be done, by adding a term in the end to our function:
![[Pasted image 20250328090952.png]]
Note: we could of course make this bias be positive as well, which would increase our sensitivity of picking up a signal

