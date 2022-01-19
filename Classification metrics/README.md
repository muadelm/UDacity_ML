# Classification Metrics

**Precision**

Precision focuses on the predicted "positive" values in your dataset. By optimizing based on precision values,
you are determining if you are doing a good job of predicting the positive values, as compared to predicting negative values as positive.
Precision = TP/(TP+FP)

**Recall**

Recall focuses on the actual "positive" values in your dataset. By optimizing based on recall values, 
you are determining if you are doing a good job of predicting the positive values without regard to how you are doing on the actual negative values. 
If you want to perform something similar to recall on the actual 'negative' values, this is called specificity (TN / (TN + FP)).
Recall = TP/(TP+FN)

**F1-score**

Averaging precision and recall
The medical model has a precision of 55.7 % and a recall of 83.3%. It's supposed to be a high-recall model.
The spam detector has a precision of 76.9 % and a recall of 37%. It's supposed to be a high-precision model.
Do we want to be carrying two numbers around all the time? We kind of want to only have one score. So the question is, how do we combine these two scores into one?

One answer is simply to take the average. Let's take the average of precision and recall.

On the left, we get 69.5 percent.
On the right, we get 56.95 percent.
And that's an okay metric, but not very different than accuracy. The way to see how this average is not the best idea is to try it in the extreme example.

`Averaging conclusion`
Averaging is not the greatest thing in principle if either precision or recall is very low. We want the number to be low even if the other one is high.

That is why Harmonic Average is best.

If the precision is one and the recall is zero, the average is 0.5, but the harmonic mean is, if we plug in the formula, zero. Another example, 
if the precision is 0.2 and the recall is 0.8, then the arithmetic mean is 0.5, but the harmonic mean is 0.32. So it's closer to the lower number.

From now on, we will not be using the average or arithmetic mean, but we'll be using the harmonic mean, and that's going to be called the F1 score, 
which is closer to the smallest value between precision and recall. If one of them is particularly low, the F1 score can raise a flag.
Fbeta =  (1+beta^2)*(Precision*Recall)/((beta^2*Precision)+Recall)
