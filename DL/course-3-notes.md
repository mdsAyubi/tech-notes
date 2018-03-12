# Structure Machine Learning Projects

## Introduction to ML strategy

### Why ML Strategy

* A lot of ideas to try out, which ones to pursue to enhance the performance of out models.

### Orthogonalization

* Chain of assumptions in ML

  * Fit training set well on cost function - bigger network, adam etc to get human level performance
  * Fit dev set well - regularization, bigger training set
  * Fit test set well - bigger dev set
  * Performs well in real world - change dev set or the cost function

## Setting up your goal

### Single metric evaluation strategy

* Use F1 score combines the precision and recall.

### Satisficing and Optimizing Metric

* Add a linear combination of accuracy and running time. Where we optimize for accuracy and running time just needs to be good enough. In this case, running time is called satisficing metric and accuracy is the optimizing metric.
* For multiple metrics, optimize one metric and other N-1 metrics are called satisficing metrics.

### Train/Dev/test distributions

* Evaluate on the dev set. Iterate quickly.
* Make sure the dev and test set come from the same distribution
