# Neural Networks and Deep Learning

## Deep L-layer network

* L - the number of layers
* n[1], n[2] - the number of neurons in a layer
* `a[l] = g[l](z[l])`
* w[l] - the weights for z[l]
* b[l] - the bias in layer l
* a[0] = x; a[L] is the predicted output of the neural network

## Forward Propagation in Deep NN

* z[1] = w[1]x + b[1]
* `a[1] = g[1](z[1])`
* Z[l] = W[1]X + b[1]
* `A[1]=g[1](Z[1])`

Z is the (Nx,M) matrix. X is all the training examples stacked vertically, therefore it is also (Nx, M) matrix. Y^ is the output vector with all the predictions stacked horizontally, i.e (1, M) matrix.

```python
Z[l] = W[l]A[l-1] + b[l]
A[l] = g[l](Z[l])

# Dimensions

Z[l] = (n[l], 1) # the activations for the neurons in the layer l stacked vertically, hence n[l] by 1
W[l] = (n[l], n[l-1]) # the number of neurons in the current layer by the number of neurons(or inputs) in the previous layer.
A[l] = (n[l-1], 1) # the number of neurons in the previous layer by 1, stacked vertically.
b[l] = (n[l], 1)

# For back prop

dw = (n[l], n[l-1])
db = (n[l], 1)

# For vectorized implementation

Z[l] = W[l]A[l-1] + b[l]

Z[l] = (n[l], m) # the z vector stacked vertically for all the training examples
W[l] = (n[l], n[l-1]) # remains the same as non vectorized version
A[l] = (n[l-1], m) # all the training examples stacked vertically
b[l] = (n[l], 1) # when added to (n[l], m) matrix, will be broadcasted into (n[l], m)

# For back props

dZ = (n[l], m)
```

## Why Deep Representation

The layers in NN are trying to figure out the relatively simpler functions first and then combining them in various forms to arrive a t a complex representation.

It is possible to show mathematically that some functions are calculate using deep networks. It will require an exponentially large shallow network to compute the same(order of 2^n).

## Forward and Backward Functions

* Layer L: w[l], b[l]
* Forward function : Input a[l-1], output a[l], using w[l], b[l]
* `z[l] = w[l]a[l-1] + b[l]; a[l] = g[l](z[l])` with cache as z[l]
* Backward FunctionL Input da[l], output da[l-1], also computing dw[l] and db[l], using w[l], b[l]

## Forward and Backward Propagation

* For any layer, input = a[l-1], output = a[l], cache z[l], w[l], b[l]
* BAck prop, for any layer l: input da[l], output = da[l-1], dw[l], db[l]

## Parameters vs HyperParameters

* Parameters: w[l], b[l]
* Hyperparameters : Learning rate, iterations, hidden layers, hidden units, activation functions.

