# MNIST_Retinotopic_Map
I use backpropagation with adam/Nesterov to train a network to recognise MNIST digits.

## Learning with a retinotopic map 
I build a 3-layer mapnet, where the middle layer is a 36-by-36 map with a field fraction of 0.25, and the connections from the middle to the output layer are dense. The activation function used in the middle layer is a "relog": $y\{\{2\}\}_i = \max( 0, sgn(v\{\{2\}\}i) log( 1 + |v\{\{2\}\}_i| ) )$. To make the final layer of the network affine, I apply a softmax function to the network's output signal. 

## Nesterov Momentum
I modify the code to learn the same task with the same map network, but using relu in place of relog, and Nesterov in place of adam. 
