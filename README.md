# MNIST and CIFAR 10 Classification using Tensorflow

- This my attempt at using Tensorflow on the MNIST ([http://yann.lecun.com/exdb/mnist/](http://yann.lecun.com/exdb/mnist/)) and CIFAR 10 ([https://www.cs.toronto.edu/~kriz/cifar.html](https://www.cs.toronto.edu/~kriz/cifar.html)) datasets.

## MNIST Classification

- I first used the MNIST classification using Tensorflow tutorial ([https://www.tensorflow.org/tutorials/](https://www.tensorflow.org/tutorials/)).
 
 + This gave an accuracy of around 97.39% after 20,000 steps.
 
 + By chaining the `GradientOptimizer` to the `AdamOptimizer` and the learning rate to `1e-3`, I was able to improve accuracy to around 99.02% after 20,000 steps. 
    
    - The `AdamOptimizer` uses moving averages of the parameters allowing it to use larger more effective steps (Bengio, 2012), which helped speed up training and improve accuracy. Choosing `1e-3` as learning rate was a product of experimentation.
 
  + The modifications made to the network architecture provided in the tutorial did not improve the accuracy.
  
## CIFAR 10 Classification

- Same as the MNIST classification, I used the CIFAR 10 classification tutorial([https://www.tensorflow.org/tutorials/images/deep_cnn](https://www.tensorflow.org/tutorials/images/deep_cnn))

 + The tutorial gave an accuracy of around 69.79% after 20,000 steps

- To improve on TensorFlow's CIFAR10 tutorial baseline accuracy of 71.62% after 2000 steps, I changed the activation functions of the two local (local 3 and local 4) fully connected layers from `relu` to `relu6`. The decision to use `relu6` was based on experimentation. I later found that Krizhevsky (2010), used  the `relu6` activation similarly on the CIFAR10 dataset.

- Aside from changing activation functions, I also moved from `GradientOptimizer` to `AdamOptimizer`. Since the `AdamOptimizer` uses smaller learning rates we changed the `INITIAL_LEARNING_RATE` from `0.1` to `0.001`. 

- From experimentation, I settled to the batch size `500`. This was also a modification from `128`.

- With all these modifications I was able to achieve an accuracy of **76.88%** after 2000 steps.

### References:

Bengio, Yoshua. *Practical Recommendations for Gradient-Based Training of Deep Architectures:Version 2*. Sept. 2012

Krizhevsky, Alex. *Convolutional Deep Belief Networks on CIFAR-10*. Aug. 2010
