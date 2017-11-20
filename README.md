# How to simulate a self driving car
This is for the Hawaii Machine Learning meetup group. The code was for Siraj Raval Youtube [video](https://youtu.be/EaY5QiZwSP4). The [original repo](https://github.com/naokishibuya/car-behavioral-cloning) was by Naoki Shibuya.

## Overview

We're going to use Udacity's [self driving car simulator](https://github.com/udacity/self-driving-car-sim) for training an autonomous car. 

## Dependencies

You can install all dependencies by running one of the following commands

You need a [anaconda](https://www.continuum.io/downloads) or [miniconda](https://conda.io/miniconda.html) to use the environment setting.

```python
# Use TensorFlow without GPU
conda env create -f environments.yml 

# Use TensorFlow with GPU
conda env create -f environment-gpu.yml
```

Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.


## Usage


### Run the pretrained model

Start up [the Udacity self-driving simulator](https://github.com/udacity/self-driving-car-sim), choose a scene and press the Autonomous Mode button.  Then, run the model as follows:

```python
python drive.py model.h5
```

### To train the model

You'll need the data folder which contains the training images.

```python
python model.py
```

This will generate a file `model-<epoch>.h5` whenever the performance in the epoch is better than the previous best.  For example, the first epoch will generate a file called `model-000.h5`.

## Credits

The credits for this code go to [naokishibuya](https://github.com/naokishibuya), Siraj also created a wrapper to get people started. I fixed what I think is a bug to hopefully ensure it runs smoothly for everyone.



