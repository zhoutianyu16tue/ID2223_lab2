# Task 1
## Q1: What loss and accuracy do you get when training over 10.000 iterations?
* The loss and accuracy with GradientDescentOptimizer and learning rate of 0.5 are 0.669694 and 0.8319 respectively; 
* The loss and accuracy with AdamOptimizer and learning rate of 0.005 are 0.585256 and 0.8402 respectively.

# Task 2
## Q1: What is the maximum accuracy that you can get in each setting for running your model with 10000 iterations?
* for the network with relu activation, the maximum accuracy on training and test set are 0.98 and 0.8841 respectively;
* for the network with sigmoid activation, the maximum accuracy on training and test set are 0.98 and 0.8821 respectively;

## Q2: Is there a big difference between the convergence rate of the sigmoid and the ReLU ? If yes, what is the reason for the difference?
Yes, ReLU a much faster convergence rate compared to sigmoid function. As can be seen from the output images for both, after around 3000 iterations, the network with ReLU has almost converged; however, the network with sigmoid activation still has the momentum to improve the test set accuracy.

The possible explanation for the difference of convergence rate is that the network with sigmoid activation suffers from the issue of vanishing gradient whereas ReLU activation gives the network more stable gradient.

## Q3: What is the reason that we use the softmax in our output layer?
The softmax layer will yield a probability distribution over all possible classes that are mutually exclusive; meantime, softmax function is differentiable, which enables gradient-based optimization.

## Q4: By zooming into the second half of the epochs in accuracy and loss plot, do you see any strange behaviour? What is the reason and how you can overcome them? (e.g., look at fluctuations or sudden loss increase after a period of decreasing loss).
* We are using AdamOptimizer and a learning rate of 0.005 in our network; this learning rate works fine in the early stage of training; however, this learning rate might be too big at later stage since the network might be oscillating around a local optima;
* another possible reason is that batch gradient descend is intrinsically unstable.

# Task 3

* Dropout(.75), AdamOptimizer, learning rate of 0.005, sigmoid activation give a test accuracy of 0.8751; the fluctuation at late stage of training is reduced, meaning the training is progressing more smoothly; more importantly, the gap between training and test accuracy, training and test cost is effectively narrowed down, which means, to some extent, we are preventing the network from overfitting;

* Learning rate decay, AdamOptimizer, , sigmoid activation give a test accuracy of 0.8817; with learning rate decay, the overfitting issue is slightly matigated;

* both, gives a test accuracy of 0.874; combining both dropout and learning rate decay effectively reduced overfitting, as can be seen from the training and test accuracy, cost plots;