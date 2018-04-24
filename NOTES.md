# Self-driving car

## Intro

Both NVidia and Udacity did it

## Procedure

Three phases:

* ?
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
