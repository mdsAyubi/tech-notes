# Neural Networks and Deep Learning

## What is a NN

- ReLU - Rectified Linear Units
- Networks created by stacking single neurons
- In s supervised learning setting, every neuron accepts the inputs from the input features - which then combine to form a complicated feature combination. Finally culminates into the output.

## Supervised Learning

- Home features - standard NN
- Advertising - standard NN
- Image recognition - CNN
- Audio - RNN
- Machine translation - RNN
- Autonomous driving - Custom/Hybrid models

## Why NNs are taking off now

- Amount of labelled data(m)
- Size of NNs
- Data, computation, algorithms(Sigmoid to ReLu activation function) innovation

## Binary Classification

- Classifying the data into a 1/0 classes.
- Image representation : 3 matrices of 64\*64 pixels - then unroll into one feature vector of length (64 by 64 by 3)
- Nx = dimensions of input feature vector
- Now we predict the classification y : 1/0
- Notation
  - (x,y) where x is Nx dimensional feature vector and y belongs to {1, 0}
  - m training examples
  - xi, yi is one training example
  - Mtest, Mtrain is the test/train examples
  - X is the matrix with all the training examples. With columns representing one training example's feature vector. X.shape = (Nx, m)
  - Y is the target vector with classification stacked as columns, i.e Y = [y1, y2, y3], 1 by m matrix. Y.shape = (1, m)

## Logistic Regression

- Predict the probability of y = 1, given x.
- Parameters are w and b, w is Nx dimensional vector and b is real number
- y = sigmoid(w'x + b), where sigmoid = 1/(1+pow(e, -z))

## Logistic Regression Cost Function

- Loss function : L(y^, y) = -(y log y^ + (1-y)log(1- y^)), applied to single training examples
- Cost function : J(w,b) = 1/m\*Sum(L(y^i, yi)), applied to all.

## Gradient Descent

- Used to minimize the cost function.
- The cost function is convex in nature : we initialize somewhere and take a step in the steepest direction to reach the global optimum.
- Repeat { w:= w - A(dJ(w, b)/dw); b := b - A(dJ(w, b)/db) }, A is the learning rate.

## Computation Graph

- Organizes the computation
- J(a,b,c) = 3(a + bc)

```python
u = b * c
v = a + u
J = 3 * v
```

## Derivatives with a computation graph

- Compute the derivatives dJ wrt the variable v, i.e dJ/dv
- Then compute the derivative dJ wrt the variable a, i.e dJ/da

## Logistic Regression With Gradient Descent

- z= w'x + b
- y^ = a = sigmoid(z)
- L(a, y) = -(y log (a) + (1-y) log(1-a))
- dz turns out to be a-y
- dw1 = x* dz, dw2 = x2* dz2, db = dz
- Update w1 = w1 - Adw1 and so on for w2 and b

## Logistic Regression on m examples

```python
J=0, dw1=0,dw2=0,db=0
for i = 1 to m:
    zi = wt * xi + b #loop or vector
    ai = sigmoid(zi)
    J += -[yi*log(ai) + (1-y)*log(1-ai)]
    dzi = ai - yi
    #n=2
    dw1 += xi * dzi
    dw2 += xi * dzi
    db += dzi

J /= m
dw1 /= m
dw2 /= m
db /= m

##vectors
w1 = w1 - alpha * dw1
w2 = w2 - alpha * dw2
b = b - alpha * db
```

## Vectorization

Avoid using explicit `for` loops. Use in built numpy capabilities for vectorized code which runs faster.

```python
#Vectorized

import numpy as np
z = np.dot(w,x) + b

# v is a vector
u = np.exp(v)
u = np.log(v)
u = np.abs(v)
u = np.maximum(v, 0)

```

## Vectorizing Logistic Regression

```python
#Z = [z1 z2 z3...zm] = wT*X + [b b b...b]
#Z = [z1 z2 z3...zm] = [wT*x1+b wT*x2 +b ...wT*xn+b]


Z = np.dot(w.T, X) + b
```

## Vectorizing Logistic Regression's Gradient Descent

```python
# A = [a1 a2 ...am]
# Y = [y1 y2 ym]

# dZ = A - Y

db = (1 / m) * np.sum(dZ)
dw = (1 / m) *  np.dot(X*dz.T)

# Therefore,
Z = np.dot(w.T, X) + b
A = sigmoid(Z)
dZ = A - Y

db = (1 / m) * np.sum(dZ)
dw = (1 / m) *  np.dot(X*dz.T)

w = w - alpha * dw
b = b - alpha * db
```

## Broadcasting in Python

- (m, n) op [(1, n) -> (m, n)] => Result
- (m, n) op [(m, 1) -> (m, n)] => Result
- (m, 1) op [R -> (m, 1)] => Result

## Numpy Vectors

- Don't create random arrays with shape as `(n,)` instead use `a = np.random.randn(5,1)`.
- Throw in assert statements to make sure your have the right shape, i.e `assert(a.shape == (5,1))`.
- Add a reshape statement when you end up with a rank-1 array for any reason, i.e `a = a.reshape((5,1))`.

## NN Representation

- Input layer, hidden layer, output layer
- Things in the hidden layer are not seen in the training set.
- Input layer isn't counted as layer.
- Activations

## Computing a NN Output

- For a node `i` in layer `l`, the notation is `a(l, i)`
- z(1,1) = w(1,1)x + b(1,1), a(1, 1) = sigmoid(z(1, 1))
- z(2,1) = w(2,1)x + b(2,1), a(2, 1) = sigmoid(z(2, 1))
- Z(1) = W(1) \* X + B(1), A(1) = sigmoid(Z(1))
- Z(2) = W(2) \* A(1) + B(2), A(2) = sigmoid(Z(2))

## Vectorizing Across Multiple Examples

- `a[2](i)` : [] represents the layer and () represents the example.
- Stack the features with (nx, m) matrix. Where nx is the features and m is the number of training examples.

```python
Z_1 = W_1*X + b_1
A_1 = sigmoid(Z_1)
Z_2 = W_2*A_1
A_2 = sigmoid(Z_2)
```

## Activation Functions

- `tanh` works better than the sigmoid function
- Centers the mean of the data to 0, learning for the next layer becomes easier.
- For the output layer, it may makes sense to use sigmoid function, binary classification for example.
- Rectified Linear Unit: `max(0. z)` for the hidden layer.
- Leaky ReLU

## Why do we need non linear activation function

- Using a linear activation function simplifies the output function and gives a linear output function. Which is not optimal as it overlooks a lot of interesting features combination in input data.
- Using a linear activation function will only compute linear output functions irrespective of the number of the hidden layers.
- Can use linear function in the output layer where the output is a real number, predicting housing prices for example.

## Derivatives of activation functions

### Sigmoid activation function

- gz(z) = 1/(1+e^(-z)), g'(z) = dg(z)/dz = g(z) \* (1 - g(z))

### Tanh activation function

- g'(z) = slope of g(z) at z = 1 - (tanh(z))^2 = 1 - a^2

### ReLU and Leaky ReLU

For ReLU

- g(z) = max(0, z)
- g'(z) = 0, if z < 0; 1, if z >= 0

For Leaky ReLU

- g(z) = max(0.01z, z)
- g'(z) = 0.01, if z < 0; 1, if z >= 0

## Gradient Descent For NN

- Parameters : w[1], b[1], w[2], b[2]
- Cost function : J(w[1], b[1], w[2], b[2]) = 1/m\*Sum(L(y^, y))
- Repeat
  - Compute prediction : (y^i, y^(i-1)...y^(m))
  - dw[1] = dJ/dw[1], db[1] = dj/db[1] ... similarly for other parameters
  - w[1] = w[1] - alpha \* dw[1]
  - b[1] = b[1] - alpha \* db[1]
  - Similarly for other parameters.
- Back prop
  - dz[2] = a[2] - y
  - dw[2] = dz[2] \* a[1]T
  - db[2] = dz[2]
  - dz[1] = w[2]T dz[2] \* g[1]'(z[1])
  - dw[1] = dz[1] . xT
  - db[1] = dz[1]

## Random Initialization

- With `0` as initial weight, all the nodes of the hidden unit will compute the same function. No matter how long the iteration continues.
- Usually multiplied with a very small number like 0.01 to land in the useful part of the activation function like tanh or sigmoid.

## Deep L-layer network

- L - the number of layers
- n[1], n[2] - the number of neurons in a layer
- `a[l] = g[l](z[l])`
- w[l] - the weights for z[l]
- b[l] - the bias in layer l
- a[0] = x; a[L] is the predicted output of the neural network

## Forward Propagation in Deep NN

- z[1] = w[1]x + b[1]
- `a[1] = g[1](z[1])`
- Z[l] = W[1]X + b[1]
- `A[1]=g[1](Z[1])`

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

- Layer L: w[l], b[l]
- Forward function : Input a[l-1], output a[l], using w[l], b[l]
- `z[l] = w[l]a[l-1] + b[l]; a[l] = g[l](z[l])` with cache as z[l]
- Backward FunctionL Input da[l], output da[l-1], also computing dw[l] and db[l], using w[l], b[l]

## Forward and Backward Propagation

- For any layer, input = a[l-1], output = a[l], cache z[l], w[l], b[l]
- BAck prop, for any layer l: input da[l], output = da[l-1], dw[l], db[l]

## Parameters vs HyperParameters

- Parameters: w[l], b[l]
- Hyperparameters : Learning rate, iterations, hidden layers, hidden units, activation functions.
