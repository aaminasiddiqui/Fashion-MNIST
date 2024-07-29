## 0verview

### Data Processing
Downloaded the dataset using Keras.
This data set includes 10 labels of different clothing types with 28 by 28 grayscale images. There is a training set of 60,000 images and 10,000 test images.

Label | Description
----- | -----------
0 | T-shirt/top
1 | Trouser
2	| Pullover
3	| Dress
4	| Coat
5	| Sandal
6	| Shirt
7	| Sneaker
8	| Bag
9	| Ankle boot
  
- Used matplotlib to view an image from the data set. It can be any image from the data set.
- Normalized the X train and X test data by dividing by the max value of the image arrays.
- Reshaped the X arrays to include a 4 dimension of the single channel. Similar to what we did for the numbers MNIST data set.
- Converted the y_train and y_test values to be one-hot encoded for categorical analysis by Keras.

### Model Training
-Used Keras to create a model consisting of the following layers
  - 2D Convolutional Layer, filters=32 and kernel_size=(4,4)

  - Pooling Layer where pool_size = (2,2)

  - Flatten Layer

  - Dense Layer (128 Neurons, but feel free to play around with this value), RELU activation

  - Final Dense Layer of 10 Neurons with a softmax activation
    
- **Input Layer**: 28x28 grayscale image
- **Convolutional Layers**: Apply multiple convolution filters to extract features.
- **Pooling Layers**: Down-sample the image dimensions while retaining important features.
- **Fully Connected Layers**: Connect every neuron in one layer to every neuron in the next layer, enabling the network to learn complex representations.
- **Output Layer**: 10 neurons corresponding to the 10 classes, typically using a softmax activation function to provide class probabilities.
  
Then compiled the model with these parameters: loss='categorical_crossentropy', optimizer='rmsprop', metrics=['accuracy']
Train/Fit the model to the x_train set for 10 epochs.

### Evaluation
The accuracy,precision,recall,f1-score the model achieved on the x_test data set are used to evaluate model performance.
