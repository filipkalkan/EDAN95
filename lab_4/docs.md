# Lab 4
## NB + GNB

### You should observe really bad results for the pure statistical NBC. Why is that the case? Presumably, many samples are (wrongly) classified as "0", why is that so, and could you add something in the evaluation (when finding the argmax) to separate "prediction failures" (image does not seem to belong to any class) from actual predictions? 

Not that bad... We added a thershold of any pixel being 5, so we had an accuracy of 0.82.

---

### Can you explain the need for the epsilon in the GNBC? What does this do and why is the approach still working?

We assume by epsilon you mean the "smoothing factor" to the variance. Without it, pixels with always value 0.0 will give mean: 0, variance: 0. Asking for the Gaussian pdf at value 0.0 gives inf. probability.

---

### What is your answer to the question whether summarising the digits data feature values into bins would improve the results for the statistical NBC? 

It was great, we binned two bins with threshold 5 (for MNIST) and it improved our score a lot.

---

### What is your answer to the question whether summarising the digits data feature values into bins would improve the results for the GNBC?

Not as neccessary as we can represent "nearby" values with the gaussian distribution.

--- 

### Can you explain why you might get problems with a straight-forward implementation of the GNBC on the non-normalised MNIST-Light data? What is this problem and why is it solved by normalisation of the data?

Not sure! It took longer for sure and was worse...

---

## All classifiers run for the data sets they should run on and produce reasonable results:

Yes.

--- 

## Can you explain your implementation / initialisation details of the EM:

### How did you set up the cluster means and variances?

Random (uniform)
### What did you use as the smoothing factor for the variance in the computation of the gaussian normal distribution?

0.2

---

### What did you observe is used as a stop criterion for the EM-iterations? Which threshold did you apply?

Euclidean distance < 1.0

---

### You get results roughly according to the following (I start with a random set of clusters, which I get by repeatedly splitting off a tenth of the data set and calculate means and variances over those; use a smoothing factor (blur) of 0.01, and a stopping threshold at 0.001):

Good!

---

### Can you explain the results intuitively? What does it mean that both variants of the same algorithm (EM) produce clusterings that are in the same ballpark neighbourhood of accuracy compared to the known targets, but that do not seem to be in agreement much more than they are with the ground truth when compared to each other? 

While k-means uses EM for its classification, it has some more "tricks". If the predictions would be almost identical, there wouldn't be any additions the K-means adds...