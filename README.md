# Neural-Style-Transfer-With-Multiple-Images

Over 90% of this code was sourced from a TensorFlow blog post that was posted in 2018. Here is the link:

https://blog.tensorflow.org/2018/08/neural-style-transfer-creating-art-with-deep-learning.html

Neural Style Transfer is an interesting subsection of Generative Modeling. When I first learned about it, it was in Deep Learning.ai's Convolutional 
Neural Networks course. Andrew Ng gave a really intuitive explanation of the Style Cost function and afterwards I read Gatys' initial paper
on Style Transfer. My first thought initially was that I wonder if by concatenating multiple images and sending them through the network, would 
the Gram Matrix for the style images learn any feature correlations between multiple images? 

I ran 4 images through the network and added a for loop at the end of the notebook that allowed for randomly ordering the images in the concatenated
volume to see if the order in which the images were concatenated had any affect on the style of the image that was mapped to the input image. Come to find out,
it does and the color and contours of the style are different for different orderings of images. It also tends to favor the images that are upfront as well.

In future, I would like to figure out why the ordering matters. Is there something with the preprocessing through the VGG19 network that causes it to collapse certain dimensions
so that it favors the front? Most of the time during transfer learning when importing a pre-trained model, it has input shape specifications so this could be the case. Also,
there are a few papers lingering in the public that have implemented Multi-style transfer and although I read them shortly after implementing this, I would like to try to
implement their models and specialized cost functions. 
