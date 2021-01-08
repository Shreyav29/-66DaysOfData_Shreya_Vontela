
# Hyper parameter tuning (Grid Search , Random Search , Bayesian Optimization)
 
## Logarithmic sampling method / Coarse search method 
-	We need to use a coarse search or logarithmic sampling method to select the range of values of a learning rate. Then you train the model for this range of leanring rates and which ever gives the best performance, that model can be chosen. 
-	In a linear sampling we chose 0 – 0.1 range with increments of 0.01 , which will give 1000 intervals. But if we do logarithmically , we get 10^-5 , 10^-4, …..10_-1 , so we just get 5 values and depending on the results we can do the tuning again in that interval. 

## Grid Search CV 
-	When we have multiple hyper parameters, you find the log sampled ranges of all parameters and then form a grid …and we compute the model accuracy for each permutation. 
-	Say there are 2 parameters X and Y , X has 5 values in range and Y has 4 values. Then we make a 5*4 grid and compute 20 models accuracy 

## Random Search 
-	In Grid search we have defined values , in random search we select the values randomly for each parameter. Say we select 5 of X and 5 of Y and compute a 25 model grid. 
-	The benefit is that here we are getting 25 models which have different X and Y values. In grid search we have 5 models with same X. So here we are doing a wider range of testing at one go. 
-	Now iteratively we tune the parameters further to get the best values

## Bayesian Optimization / Black box optimization 
-	This is a high computation method. It is only used when model is very simple and computation is easy or when model is very complex and we need the best values. 
-	This gives the best possible estimates
-	Here the model first runs through a burn out period where it generates random samples like the random search method and establishes a probability distribution of the accuracy over the parameters. Depending on which range of parameters are giving better values(priors), it calculates the next posterior value of the parameters. Now in the next step these posteriors become the priors and we get the next best possible posteriors. This way it gets the best estimates. 


