# MNIST and CIFAR 10 Classification using Tensorflow

- This my attempt at using Tensorflow on the MNIST ([http://yann.lecun.com/exdb/mnist/](http://yann.lecun.com/exdb/mnist/)) and CIFAR 10 ([https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)) datasets.

## MNIST classification

- I first used the MNIST classification using Tensorflow tutorial ([https://www.tensorflow.org/tutorials/](https://www.tensorflow.org/tutorials/)).
 
 + This gave an accuracy of around 97.39% after 20,000 steps.
 
 + By chaning the `GradientOptimizer` to the `AdamOptimizer` and the learning rate to `1e-3`, I was able to improve accuracy to around 99.02% after 20,000 steps. 
    
    - The `AdamOptimizer` uses moving averages of the parameters allowing it to use larger more effective steps (Bengio, 2012), which helped speed up training and improve accuracy. Choosing `1e-3` as learning rate was a product of experimentation.
 
  + The modifications made to the network architecture provided in the tutorial did not improve the accuracy.
