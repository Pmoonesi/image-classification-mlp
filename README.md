# image-classification-mlp
This is the first project for the course Computational Intelligence - Spring 2022, Dr. Ebadzadeh

## introduction
I used a 4 layer multilayered perceptron model to classify images in CIFAR-10 dataset (publicly available [here](https://www.cs.toronto.edu/~kriz/cifar.html)).

For the model we have 1024 neurons for the input layer, 16 neurons for each of the two hidden layers and 4 neurons for output layer to be able to classify only 4 classes of CIFAR-10 dataset. For the activation function I used sigmoid in every layer and for the cost function I used sum of squared errors(SSE).

To train the model I used a stochastic gradient descent algorithm and implemented two methods to compute gradient; vectorized and non-vectorized.

## preparing the data
Our model has 4 neurons in it's last layer so we needed to provide it with 4 classes of CIFAR-10 dataset. To do this, I used a function called [load_cifar_10_data](https://github.com/snatch59/load-cifar-10/blob/master/load_cifar_10.py) to load the cifar dataset. Then I extracted the data and their labels for the first four classes including cat, bird, automobile and airplane.
For the model to be able to use this data, we first transform images to grayscale (otherwise we needed one neuron for each color, 3072 neurons in the first layer), then we flatten the images. After these operations we can use the data to train and test our model.

## structure
You need to extract the CIFAR-10 dataset files into cifar-10-batches-py folder and have your structure like down below.

    .
    ├── ...
    ├── cifar-10-batches-py                    
    │   ├── batches.meta          
    │   ├── data_batch_1  
    │   ├── ...
    │   ├── data_batch_5        
    │   └── test_batch               
    └── mlp.ipynb

## how to run
```
pip install notebook
jupyter notebook
```