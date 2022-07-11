# Machine Learning System Identification

This repository is a store of implementations created to identify various system parameters using machine learning techniques.

## Organization

A tree structure with parent directories indicating the problem being tackled, followed by a directory naming the subgroup of implementations and framework they use. These implementation directories house subdirectories that signal the type of data the programs in the directory use as input. More detail about each implementation' input and output can be found in the "Documentation" section. 

## Documentation

### "Autoencoder Torch"/"Complex Plane"/AE.ipynb

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 200 by 200 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" contains a 2D matrix of 6 parameters by the number of samples we have.

The model outputs 6 parameters that each represent a component in the ladder network.

### "CNN FC NN Keras"/"Complex Plane"/AN.ipynb

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 100 by 100 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" contains a 2D matrix of 6 parameters by the number of samples we have.

The model outputs 6 parameters that each represent a component in the ladder network.

