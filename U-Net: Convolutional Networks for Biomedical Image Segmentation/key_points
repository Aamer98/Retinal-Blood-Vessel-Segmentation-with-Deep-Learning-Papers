U-Net: Convolutional Networks for Biomedical Image Segmentation
    • Down convolutions capture context
    • Up convolutions capture precise localisation
    • The down convolution part ( the encoder ) is a regular CNN architecture.
    • This is followed by up sampling convolutional layers ( the decoder )
    • Features from contracting path are combined with the up-sampled output for localisation.
    • Large number of feature channels to propagate features to higher resolution layers.. The contracting path symmetric to expanding path.
    • No fully connected layers.
    • Only valid part for each convolutions
    • Data augmentation used due to lack of data
    • A weighted loss, where the separating background labels between touching cells obtain a large weight in the loss function.
    • Architecture
        ◦ Down Conv
        ◦ 3x3 unpadded convolutions followed by ReLU with a 2x2 max pooling with a stride of 2
        ◦ At each step, the number of feature channels doubled
        ◦ Up Conv
        ◦ 2x2 convolution that halves the number of feature channels.
        ◦ Concatenation of feature map (cropped) from downsampling part followed by 2 3x3 conv layers each followed by ReLU
        ◦ At final layer, a 1x1 convolution is used to map each 64 component vector to desired number of classes. 
        ◦ Total: 23 conv layers
        ◦ batch size:1
        ◦ momentum:0.99
        ◦ softmax over final layer
        ◦ cross entropy loss function
        ◦ Weight initialisation: gaussian distribution with standard deviation of sq_root(2/N)
    • Data Augmentation
        ◦ In microscopial images, we need shift and rotation invariance as well as robustness to deformations and gray value variations
        ◦ Random elastic deformations of the training samples seem to be the key concept
        ◦ Smooth deformations using random displacement vectors in a 3x3 grid. The displacement vectors are sampled from a gaussian distribution with 10 pixel standard deviation. Per pixel displacement is then computed using bicubic interpolation. 
        ◦ Drop out layers at the end of contracting path perform further implicit data augmentation.

