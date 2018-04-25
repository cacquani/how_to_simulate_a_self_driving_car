# Self-driving car

## Intro

Both NVidia and Udacity did it

## Procedure

Three phases:

* Generate data
* Training
* Testing

### ?

### Training

Supervised learning algorithms.

Car, Three cameras (front, left and right) and a lot of laps (72hrs)

Reduce the differences between what the human does and what the car thinks it
should do.

* Steering angle
* Throttle
* Brake
* Speed

(simplified to just the steering angle for today)

### Testing

Does it crash?

* Yes -> failure (try again)
* No -> success

Can expand to 'does it stay on the road' :)

We're going to communicate using a server-client architecture

Server -> the simulator (Udacity)
Client -> car brain

## Links

* (Github)[https://github.com/samsammurphy/How_to_simulate_a_self_driving_car]
* (Udacity)[https://github.com/udacity/self-driving-car-sim]
* (Tensorflow)[https://www.tensorflow.org/]

## Setup

  conda env create -f environments.yml
  source activate car-behavioral-cloning

  conda install tensorflow

## The Model

Machine learning models general idea:

y = brains(X)

where

y = label (how to drive)

X = input (images)

Keras -> python machine learning library

Everything arranged in layers

2d convolution layer -> lookup on wikipedia

* image input
* filter aka kernel
* dot product
* move along
* repeat
* outputs a new layer

* Neurons are only locally connected (i.e. in width and height)
* less computationally expensive (images too large for full connection)
* can find spatial patterns
* much better at generalised learning (fully connected overfit)

What is a fully connected layer? (as opposite to 2d convolution layer)

* Traditional
* Every single neuron is connected to every other neuron


  model.add(Conv2D(24, 5, 5, activation='elu', subsample=(2, 2)))

2d convolution layer
24 sets of random weights
5x5 pixels kernel
exponential linear unit activation function
shift 2x, 2y every iteration

  model.add(Dropout(args.keep_prob))

How many nodes are randomly ignored
Helps prevent over-fitting
speeds up training

  model.add(Flatten())

flatten the data at the dropout rate

  model.add(Dense(100, activation='elu'))

Fully connected layer (after a few passages on a 2d convolution
