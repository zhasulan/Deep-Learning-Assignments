# **Week 2 Quiz - Optimization algorithms** #

1. Which notation would you use to denote the 3rd layer’s activations when the input is the 7th example from the 8th minibatch?

	- [ ] ![](http://latex.codecogs.com/gif.latex?a%5E%7B%5B3%5D%5C%7B7%5C%7D%288%29%7D)
	- [ ] ![](http://latex.codecogs.com/gif.latex?a%5E%7B%5B8%5D%5C%7B7%5C%7D%283%29%7D)
	- [x] ![](http://latex.codecogs.com/gif.latex?a%5E%7B%5B3%5D%5C%7B8%5C%7D%287%29%7D)
	- [ ] ![](http://latex.codecogs.com/gif.latex?a%5E%7B%5B8%5D%5C%7B3%5C%7D%287%29%7D)

2. Which of these statements about mini-batch gradient descent do you agree with?

	- [x] One iteration of mini-batch gradient descent (computing on a single mini-batch) is faster than one iteration of batch gradient descent.
	- [ ] Training one epoch (one pass through the training set) using mini-batch gradient descent is faster than training one epoch using batch gradient descent.
	- [ ] You should implement mini-batch gradient descent without an explicit for-loop over different mini-batches, so that the algorithm processes all mini-batches at the same time (vectorization).

3. Why is the best mini-batch size usually not 1 and not m, but instead something in-between?

	- [x] If the mini-batch size is 1, you lose the benefits of vectorization across examples in the mini-batch.
	- [ ] If the mini-batch size is m, you end up with stochastic gradient descent, which is usually slower than mini-batch gradient descent.
	- [ ] If the mini-batch size is 1, you end up having to process the entire training set before making any progress.
	- [x] If the mini-batch size is m, you end up with batch gradient descent, which has to process the whole training set before making progress.

4. Suppose your learning algorithm’s cost ***J***, plotted as a function of the number of iterations, looks like this:

	![](https://raw.githubusercontent.com/zhasulan/Deep-Learning-Assignments/master/2%20Improving%20Deep%20Neural%20Networks%20Hyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week%206/images/mini-batch-cost.png)

	- [x] If you’re using mini-batch gradient descent, this looks acceptable. But if you’re using batch gradient descent, something is wrong.
	- [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, this looks acceptable.
	- [ ] If you’re using mini-batch gradient descent, something is wrong. But if you’re using batch gradient descent, this looks acceptable.
	- [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, something is wrong.

5. Suppose the temperature in Casablanca over the first three days of January are the same:

	Jan 1st: ![](http://latex.codecogs.com/gif.latex?%5Ctheta%20_%7B1%7D%20%3D%2010%5E%7B%5Ccirc%7DC)
	
	Jan 2nd: ![](http://latex.codecogs.com/gif.latex?%5Ctheta%20_%7B2%7D10%5E%7B%5Ccirc%7DC)
	
	(We used Fahrenheit in lecture, so will use Celsius here in honor of the metric world.)
	
	Say you use an exponentially weighted average with ![](http://latex.codecogs.com/gif.latex?%5Cbeta%3D0.5) to track the temperature: ![](http://latex.codecogs.com/gif.latex?v_%7B0%7D%3D0%2Cv_%7Bt%7D%3D%5Cbeta%20v_%7Bt-1%7D&plus;%281-%5Cbeta%29%5Ctheta_%7Bt%7D). If ![](http://latex.codecogs.com/gif.latex?v_%7B2%7D) is the value computed after day 2 without bias correction, and vcorrected2 is the value you compute with bias correction. What are these values? (You might be able to do this without a calculator, but you don't actually need one. Remember what is bias correction doing.)

	- [x] ![](http://latex.codecogs.com/gif.latex?v_%7B2%7D%3D7.5%2C%20v_%7B2%7D%5E%7Bcorrected%7D%3D10)
	- [ ] ![](http://latex.codecogs.com/gif.latex?v_%7B2%7D%3D10%2C%20v_%7B2%7D%5E%7Bcorrected%7D%3D10)
	- [ ] ![](http://latex.codecogs.com/gif.latex?v_%7B2%7D%3D7.5%2C%20v_%7B2%7D%5E%7Bcorrected%7D%3D7.5)
	- [ ] ![](http://latex.codecogs.com/gif.latex?v_%7B2%7D%3D10%2C%20v_%7B2%7D%5E%7Bcorrected%7D%3D7.5)

6. Which of these is NOT a good learning rate decay scheme? Here, t is the epoch number.

	- [x] ![](http://latex.codecogs.com/gif.latex?%5Calpha%20%3De%5E%7Bt%7D%5Calpha_%7B0%7D)
	- [ ] ![](http://latex.codecogs.com/gif.latex?%5Calpha%20%3D%5Cfrac%7B1%7D%7B%5Csqrt%7Bt%7D%7D%5Calpha_%7B0%7D)
	- [ ] ![](http://latex.codecogs.com/gif.latex?%5Calpha%20%3D0.95%5E%7Bt%7D%5Calpha_%7B0%7D)
	- [ ] ![](http://latex.codecogs.com/gif.latex?%5Calpha%20%3D%5Cfrac%7B1%7D%7B1&plus;2*t%7D%5Calpha_%7B0%7D)

7. You use an exponentially weighted average on the London temperature dataset. You use the following to track the temperature: ![](http://latex.codecogs.com/gif.latex?v_%7Bt%7D%3D%5Cbeta%20v_%7Bt-1%7D&plus;%281-%5Cbeta%29%5Ctheta_%7Bt%7D). The red line below was computed using ![](http://latex.codecogs.com/gif.latex?%5Cbeta%3D0.9). What would happen to your red curve as you vary ![](http://latex.codecogs.com/gif.latex?%5Cbeta)? (Check the two that apply)

	![](https://raw.githubusercontent.com/zhasulan/Deep-Learning-Assignments/master/2%20Improving%20Deep%20Neural%20Networks%20Hyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week%206/images/d_temp.png)

	- [ ] Decreasing ![](http://latex.codecogs.com/gif.latex?%5Cbeta) will shift the red line slightly to the right.
	- [x] Increasing ![](http://latex.codecogs.com/gif.latex?%5Cbeta) will shift the red line slightly to the right.
	- [x] Decreasing ![](http://latex.codecogs.com/gif.latex?%5Cbeta) will create more oscillation within the red line.
	- [ ] Increasing ![](http://latex.codecogs.com/gif.latex?%5Cbeta) will create more oscillations within the red line.

8. Consider this figure:
	
	![](https://raw.githubusercontent.com/zhasulan/Deep-Learning-Assignments/master/2%20Improving%20Deep%20Neural%20Networks%20Hyperparameter%20tuning%2C%20Regularization%20and%20Optimization/Week%206/images/f1_GD.png)

	These plots were generated with gradient descent; with gradient descent with momentum (![](http://latex.codecogs.com/gif.latex?%5Cbeta%3D0.5)) and gradient descent with momentum (![](http://latex.codecogs.com/gif.latex?%5Cbeta%3D0.9)). Which curve corresponds to which algorithm?


	- [x] (1) is gradient descent. (2) is gradient descent with momentum (small ![](http://latex.codecogs.com/gif.latex?%5Cbeta)). (3) is gradient descent with momentum (large ![](http://latex.codecogs.com/gif.latex?%5Cbeta))
	- [ ] (1) is gradient descent. (2) is gradient descent with momentum (large ![](http://latex.codecogs.com/gif.latex?%5Cbeta)) . (3) is gradient descent with momentum (small ![](http://latex.codecogs.com/gif.latex?%5Cbeta))
	- [ ] (1) is gradient descent with momentum (small ![](http://latex.codecogs.com/gif.latex?%5Cbeta)), (2) is gradient descent with momentum (small ![](http://latex.codecogs.com/gif.latex?%5Cbeta)), (3) is gradient descent
	- [ ] (1) is gradient descent with momentum (small ![](http://latex.codecogs.com/gif.latex?%5Cbeta)). (2) is gradient descent. (3) is gradient descent with momentum (large ![](http://latex.codecogs.com/gif.latex?%5Cbeta))

9. Suppose batch gradient descent in a deep network is taking excessively long to find a value of the parameters that achieves a small value for the cost function ![](http://latex.codecogs.com/gif.latex?J%28W%5E%7B1%7D%2Cb%5E%7B1%7D%2C...%2CW%5E%7BL%7D%2Cb%5E%7BL%7D%29). Which of the following techniques could help find parameter values that attain a small value for ![](http://latex.codecogs.com/gif.latex?J)? (Check all that apply)

	- [x] Try mini-batch gradient descent
	- [ ] Try initializing all the weights to zero
	- [x] Try tuning the learning rate ![](http://latex.codecogs.com/gif.latex?%5Calpha)
	- [x] Try better random initialization for the weights
	- [x] Try using Adam

10. Which of the following statements about Adam is False?

	- [x] Adam should be used with batch gradient computations, not with mini-batches.
	- [ ] The learning rate hyperparameter ![](http://latex.codecogs.com/gif.latex?%5Calpha) in Adam usually needs to be tuned.
	- [ ] Adam combines the advantages of RMSProp and momentum
	- [ ] We usually use “default” values for the hyperparameters ![](http://latex.codecogs.com/gif.latex?%5Cbeta1),![](http://latex.codecogs.com/gif.latex?%5Cbeta2) and ε in Adam (![](http://latex.codecogs.com/gif.latex?%5Cbeta1%3D0.9), ![](http://latex.codecogs.com/gif.latex?%5Cbeta2%3D0.999), ![](http://latex.codecogs.com/gif.latex?%5Cepsilon%3D10%5E%7B-8%7D))