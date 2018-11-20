# Structure Machine Learning Projects

## Introduction to ML strategy

### Why ML Strategy

- A lot of ideas to try out, which ones to pursue to enhance the performance of out models.

### Orthogonalization

- Chain of assumptions in ML

  - Fit training set well on cost function - bigger network, adam etc to get human level performance
  - Fit dev set well - regularization, bigger training set
  - Fit test set well - bigger dev set
  - Performs well in real world - change dev set or the cost function

## Setting up your goal

### Single metric evaluation strategy

- Use F1 score combines the precision and recall.

### Satisficing and Optimizing Metric

- Add a linear combination of accuracy and running time. Where we optimize for accuracy and running time just needs to be good enough. In this case, running time is called satisficing metric and accuracy is the optimizing metric.
- For multiple metrics, optimize one metric and other N-1 metrics are called satisficing metrics.

### Train/Dev/test distributions

- Evaluate on the dev set. Iterate quickly.
- Make sure the dev and test set come from the same distribution

### Size of dev and test set

- Common for 98% train and 1% dev and test set with a large data set, say around 1M.
- Set test size big enough to give high confidence.

### Changing dev and test sets metric

- If the model does not conform to the preferences of the audience, it might be the time to see and correct the evaluation metric. May be add weights to the error term which punishes heavily when the algorithm makes an unacceptable mistake.
- Place the target as one step, and aiming fot the target as another target.
- If doing well on the dev/test metric does not correspond to doing well in the application. Change the metric and/or the dev/test set.

## Comparing to Human Level Performance

### Why human level performance

- Bayes Optimal error : the minimum achievable error for any function mapping x -> y.
- Till the time the algorithm is doing worse than humans, we can get more labelled data from humans, gain insight from manual error analysis, better analyse bias/variance.

### Understanding Human Level performance

- Human level error as a proxy for Bayes error.
- Means different things in different contexts.

### Improving the model performance

- Fot the train set well.
- Generalizes well to the dev set
- Look at human level -> training error(avoidable bias) -> dev error(variance)
- Training bigger model, train longer/better algorithm, better architecture, hyper parameters can solve avoidable bias problem
- Getting more data, regularization, data augmentation, various NN architectures/hyper parameters for the variance problem.

## Error Analysis

### Carrying out error analysis

- Take a look at the error and see how much percentage gain in error could e achieved solving the problem.
- For multiple ideas to evaluate in parallel, make a spread sheet and asses what error categories are affecting what examples. Based on the count, decide to work on a particular error category.

### Cleaning Up Incorrectly Labelled Data

- DL is robust to random errors but not for systematic errors.
- It might make sense to manually count the error and then make decisions.
- Correct the labels on the train set to extract the some bits of performance.
- Consider to check examples which the algorithm got right as well.

### Build your first system quickly then iterate

- Setup the dev test metric first
- Build the system quickly
- Use bias and variance and error analysis to prioritize next steps.
