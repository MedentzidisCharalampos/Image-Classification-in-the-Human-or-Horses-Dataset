# Image-Classification-in-the-Human-or-Horses-Dataset
The dataset:

Horses or Humans is a dataset of 300×300 images. The set contains 500 rendered images of various species of horse in various poses in various locations. It also contains 527 rendered images of humans in various poses and locations. Emphasis has been taken to ensure diversity of humans, and to that end there are both men and women as well as Asian, Black, South Asian and Caucasians present in the training set. The validation set adds 6 different figures of different gender, race and pose to ensure breadth of data. The dataset can be found at this URL:  https://www.kaggle.com/sanikamal/horses-or-humans-dataset. 

The Preprocessing of the dataset:
We set up data generators that will read pictures in our source folders, convert them to float32 tensors, and feed them (with their labels) to our network. We'll have one generator for the training images and one for the validation images. Our generators will yield batches of images of size 300x300 and their labels (binary).  We will preprocess our images by normalizing the pixel values to be in the [0, 1] range (originally all values are in the [0, 255] range).

The architecture of the model:
1. A Convolutional Layer with 16 filters, 3 x 3 kernel size, Relu activation function and (300, 300, 3) as input size
2. A Pooling Layer with 2 x 2 window and Max Pool
3. A Convolutional Layer with 32 filters, 3 x 3 kernel size, Relu activation function
4. A Pooling Layer with 2 x 2 window and Max Pool
5. A Convolutional Layer with 64 filters, 3 x 3 kernel size, Relu activation function
6. A Pooling Layer with 2 x 2 window and Max Pool
7. A Convolutional Layer with 64 filters, 3 x 3 kernel size, Relu activation function
8. A Pooling Layer with 2 x 2 window and Max Pool
9. A Convolutional Layer with 64 filters, 3 x 3 kernel size, Relu activation function
10. A Pooling Layer with 2 x 2 window and Max Pool
11. A Flatten Layer tha squash the the output of the previous layer into a 1D dimension
12. A Dense Layer with 512-units and Relu activation function
13. A Dense Layer with 1-units and Sigmoid activation function

We will train our model with the binary_crossentropy loss, because it's a binary classification problem and our final activation is a sigmoid.   
We will use the rmsprop optimizer with a learning rate of 0.001.   
Using the RMSprop optimization algorithm is preferable to stochastic gradient descent (SGD), because RMSprop automates learning-rate tuning for us.  

Training:

The model is trained for 15 epochs. The Loss and Accuracy are a great indication of progress of training. It's making a guess as to the classification of the training data, and then measuring it against the known label, calculating the result. Accuracy is the portion of correct guesses.

The Result:

The accuracy is 92.88 % and the validation accuracy is 84.38 %. 



