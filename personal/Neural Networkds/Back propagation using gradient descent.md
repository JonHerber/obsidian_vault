# Broad overview

Back propagation basically works like this:
```pseudo
```pseudo
\begin{algorithm}
\caption{Backpropagation}
\begin{algorithmic}
  \Procedure{Backpropagation}{$X, Y, \eta, T$}
    \State Initialize weights $W^{[l]}, b^{[l]}$ for each layer $l$
    \For{epoch = 1 to $T$}
      \For{each training example $i = 1 \to m$}
        \State \textbf{Forward Propagation:}
        \For{layer $l = 1 \to L$}
          \State $Z^{[l]} \gets W^{[l]} A^{[l-1]} + b^{[l]}$
          \State $A^{[l]} \gets \sigma(Z^{[l]})$ \Comment{Activation function $\sigma$}
        \EndFor

        \State \textbf{Compute Loss:}
        \State $L \gets \frac{1}{2} \| A^{[L]} - y^{(i)} \|^2$

        \State \textbf{Backward Propagation:}
        \State Compute error for output layer: 
        \State $\delta^{[L]} \gets A^{[L]} - y^{(i)}$
        \For{layer $l = L-1$ to $1$}
          \State Compute error for hidden layers:
          \State $\delta^{[l]} \gets (W^{[l+1]})^T \delta^{[l+1]} \cdot \sigma'(Z^{[l]})$
        \EndFor

        \State \textbf{Gradient Descent:}
        \For{layer $l = 1$ to $L$}
          \State Compute gradients:
          \State $\frac{\partial L}{\partial W^{[l]}} \gets \delta^{[l]} (A^{[l-1]})^T$
          \State $\frac{\partial L}{\partial b^{[l]}} \gets \delta^{[l]}$
          \State Update weights and biases:
          \State $W^{[l]} \gets W^{[l]} - \eta \frac{\partial L}{\partial W^{[l]}}$
          \State $b^{[l]} \gets b^{[l]} - \eta \frac{\partial L}{\partial b^{[l]}}$
        \EndFor
      \EndFor
    \EndFor
  \EndProcedure
\end{algorithmic}
\end{algorithm}

```

- [ ] wdh & selbst implementieren MIT VISUALISIERUNG!


