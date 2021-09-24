# TSAI-END3
TSAI course on Extensive NLP using Deep learning models

# Assignment 1 
### What is a neural network neuron?
A neural network neuron (as against a neuron in a human brain) is a computational abstraction which is used to create and model neural networks used for various 
machine learning applications. A neuron consists of a "memory state" (or a "signal") and an external "computational unit" which consists of "weights" and an "activation function". It receives inputs via external connections (to incoming layer of neurons) which are weighted with the incoming weights, and outputs are fed to the next layer of neurons via 
the corresponding weights. The incoming weighted inputs are summed and passed through the activation function to generate the output and the process is followed layer by layer to achieve the "forward pass".
### What is the use of the learning rate?
The Learning rate controls the scaling factor used to update the weights based on the gradient of the error with respect to the weight. The LR should be chosen (with trial and error or a learning schedule) to ensure that it is not too low or too high. Being too low will lead to very slow convergence while being too high may lead to instability as 
we traverse the error/loss landscape with each update.
### How are weights initialized?
The weights are usually initialized randomly with a normal distribution to small values. We need randomization to break symmetry (else all weights will be updated the same way). 
We need small weights else there may be overflow (we get large values as inputs propagate through the network multipled by large weights causing an exponential growth - also known as the problem of exploding gradients). They should also not be too low as it may cause the problem of vanishing gradients where (smaller values multiplied will cause the values to exponentially reduce to zero). Techniques like normalization are needed to avoid both.
### What is "loss" in a neural network?
Loss it the mismatch between the expected output for a given input and the output that a given network (with a specific set of parameters) predicts. Loss could be of vairous types including a simple absolute value of difference (L1 loss) or mean squared error (L2 loss) or more advanced types like cross entropy loss.
### What is the "chain rule" in gradient flow?
The chain rule in gradient flow helps predict the partial derivative of the error with respect to any weight inside a deep NN, by propagating it (in a chain) from the outermost layers (closest to the output) to the "inner" layers - closer to the input. It is based on the chain rule of differentiation used in calculus.
