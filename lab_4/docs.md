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

## EM
