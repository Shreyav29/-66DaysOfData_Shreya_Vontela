# Difference between Gradient Descent(Batch GD) , Stochastic Gradient descent and Mini Batch Gradient Descent 
- Today I studied the difference between the three commonly used gradient descents. Below is my understanding. 

## Gradient Descent 
Gradient descent is an optimization algorithm that's used when training a machine learning model. It follows a pricess where the parameter weights are tweaked iteratively to minimise the given loss function , till it reaches a local minimum. Here during each iteration we calculate the gradient of the loss function wrt the entire training data and update the parameters in the opposite direction of the gradient. 

The magnitude of update depends on the leanring rate of the model. A high leanring rate helps you to converge faster but it might miss out the minimum loss location. A small leanring rate can give you the optimal loss value but might take more time . 

But  In case of very large datasets, using GD can be quite costly because we need to store the entire data in order to compute the graients.

## Stochastic Gradient descent
In SGD we randomly select one training sample in each iteration and we update the weights as per that training sample gradients. Due to its stochastic nature, the path towards the global cost minimum is not "direct" as in GD, but may go "zig-zag". But due to the random nature, we converge to the optimal value in less number of epochs but might require more iterations in those few epochs. Also as we do it for one sample at a time we cannot use vectorized approaches. 

## Mini Batch Gradient Descent 
Mini-Batch Gradient Descent is a compromise between batch GD and SGD. Here we update the model based on smaller groups of training samples; instead of computing the gradient from 1 sample (SGD) or all n training samples (GD), we compute the gradient from 1 < k < n training samples (a common mini-batch size is k=50).
This converges in fewer epochs than GD because we update the weights more frequently and it will also not need a lot of memory like GD as we are only storing each batch at a time. It would also not need to do as many iterations as it does in SGD per epoch, because due to the batch method it is not as zig zag as SGD.  It also  uses the vectorized operation, which typically results in a computational performance gain over SGD.


