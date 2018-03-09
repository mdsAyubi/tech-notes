# Improving Neural Networks

## Setting Up ML Application

### Iterative process

* Too many hyper parameters hidden layers, units in hidden layer, learning rate, activation function
* Data usually split into train, dev and test sets
* In the era of big data, usually, the dev data set is small, around 1% of the total data set. Just enough to evaluate multiple algorithms.
* Make sure the dev and test sets come from the same distribution.

### Bias and Variance

* High bias will under fit the data as it makes assumptions about the shape of the output function which might not be true.
* High variance will over fit the data as it tries to classify every training example.
* The decision boundary lies in between the two.
* Suppose train set error is 1% and dev set error is 11%, it means the function has over fit the training data and is not generalizing well. This is called high variance.
* Suppose the algorithm has a high error rate on the train set and almost similar error rate in test set. It means the algorithm is not even fitting the train set correctly, it might be making some assumptions regarding the shape of the decision boundary. This is called bias.
* A high error rate in the train set and a alarmingly high error rate in the test set signals high bias and high variance. The worst.

### Basic Recipe for ML

* High bias (performance on training data) -> bigger network, train longer, different NN architecture
* High variance (performance on dev/test data) -> more data, regularization, different NN architecture.

## Regularizing Your NN

### Regularization

* With respect to the Logistic Regression loss function, we add a parameter to the loss function, which `w.Tw`
* Since `b` is just a number as compared to the high dimensional vector `w`, adding params for `b` is not much helpful. But can be done.
* L1 regularization can also be performed where the parameter that is added is just `(lambda / 2*m) * ||w||`
* For NN, to regularize, the quantity added is the Frobenius norm, which is `(lambda / 2m)*Sum[1, L](Sum[1,i](Sum[1,j](W[i,j])^2))`
* Similarly added to the back prop step.

### Why regularization prevents over fitting

* Cranking the regularization param very will offset the effects of a lot of hidden units, i.e zero them out. And move the architecture towards a more simplified NN. Which will remove the over fitting caused by the complicated NN.
* If suppose we are using `tanh` as the activation function, then using the regularization will reduce the `w` matrix to have smaller values which will in turn cause the `z` to be small. This will force the usage of the linear part of the `tanh(z)` function. Thus the NN will move towards a linear decision boundary instead of a complicated non linear shape.

### Drop out regularization

* A coin toss decides which nodes to remove. Which results in a much simpler NN. - WIA
* Can not rely on any one feature.
* The keep probability can be varied across layers. Usually in the layers with the more hidden units.
* Can also be applied the input layer.

### Other regularization techniques

* Data augmentation : Add more versions of training examples
* Early stopping

## Setting up Optimization Problem

### Normalizing inputs

* Usually subtract mean and divide by variance. Use the same mu and sigma for test set as well.
* Normalizing the input features to the same scale gives a better, more symmetric shape to the cost function and gradient descent converges faster.

### Vanishing and Exploding Gradients

* The case where the derivatives are very very large or exponentially small.
* With very deep networks if `w[l]` is greater than or less than I(identity matrix), the derivative or the slope for gradient descent can become very large or very small.

### Weight Initialization for Deep Networks

* Usually the weight matrix is setup with the following code `w[l] = np.random.randn(shape) * np.sqrt(2 / n[l-1])`.
* The above sets the variance of the weight matrix to `2 / n`
* Tune the other hyper parameters first before tuning the initialization of weights.

### Gradient Checking

* Take w[l], b[l] and reshape them into a vector theta.
* Again, take dw[l] and db[l] and reshape into a vector d_theta of the same shape as theta
* `for each i: d_theta_approx = J(theta_1, theta_2, theta_i + e...) - J(theta_1, theta_2, theta_i - e, ...) / 2*e`
* Turns out, `d_theta_approx ~ dJ/d_theta`
* The check if `||d_theta_approx - d_theta||_2 / (||d_theta_approx||_2 + ||d_theta||_2)` ~ 10e-7 then great when e = 10e-7

### Implementation notes

* Only use to debug not to train
* If algorithm fails grad check, look at the components to try to identify the bug
* Remember regularization if used. Used it.
* Does not work with drop out.
* Run at random initialization, perhaps again after some training.
