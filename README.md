# Machine Learning System Identification

This repository is a store of implementations created to identify various system parameters using machine learning techniques.

## Organization

A tree structure with parent directories indicating the problem being tackled, followed by a directory naming the subgroup of implementations and framework they use. These implementation directories house subdirectories that signal the type of data the programs in the directory use as input. More detail about each implementation' input and output can be found in the "Documentation" section.

## Documentation

### "Autoencoder Torch"/"Complex Plane"/AE.ipynb

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 200 by 200 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" contains a 2D matrix of 6 parameters by the number of samples we have.

The model outputs 6 parameters that each represent a component in the ladder network.

#### Procedure and Results

Two channel data of the appropriate size for the program was generated and inputted. The total size of the dataset is 1000 samples, with 800 of them being used for training and the rest are used for testing. The data was generated using matlab (Code will be provided soon).

The results predicted by the model for each of the parameters can be seen in the scatter plots below, 

![AE Results](Autoencoder%20Torch/Complex%20Plane/Results/AE%20Results.png)

The absolute mean error for this model in this case was an average of 8% for all the parameters.

### "CNN FC NN Keras"/"Complex Plane"/AN.ipynb

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 100 by 100 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" contains a 2D matrix of 6 parameters by the number of samples we have.

The model outputs 6 parameters that each represent a component in the ladder network.

#### Procedure and Results

Two channel data of the appropriate size for the program was generated and inputted. The total size of the dataset is 500 samples, with 300 of them being used for training and the rest are used for testing. The data was generated using matlab (Code will be provided soon).

The results are predicted by the model for each of the parameters can be seen in the scatter plots below,

![AN Results](CNN%20FC%20NN%20Keras/Complex%20Plane/Results/AN%20Results.png)

The absolute mean error for each of the parameters in this model' prediction ranged between 61% at the worst and 24% at best. The average error for all parameters was an average of around 30%.