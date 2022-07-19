# Machine Learning System Identification

This repository is a store of implementations created to identify various system parameters using machine learning techniques.

## Organization

A tree structure with parent directories indicating the problem being tackled, followed by a directory naming the subgroup of implementations and framework they use. These implementation directories house subdirectories that signal the type of data the programs in the directory use as input. More detail about each implementation' input and output can be found in the "Documentation" section.

## Documentation

### "Autoencoder Torch"/"Complex Plane"/AE.ipynb

This is an autoencoder implementation that consists of an autoencoder stage and a fully connected layer stage. Firstly, the autoencoder down samples images to a 64 element vector of values. Using said vector the autoencoder then attempts to reconstruct the original images. The 64 element vector should now contain important information about the original image, and is then fed into a fully connected network with an output of the 6 target parameters.

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 200 by 200 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" is a 3D matrix containing vectors of 6 parameters.

The model outputs 6 parameters that each represent a component in the ladder network.

#### Procedure and Results

Two channel data of the appropriate size for the program was generated and inputted. The total size of the dataset is 1000 samples, with 800 of them being used for training and the rest are used for testing. The data was generated using matlab (Code will be provided soon).

The results predicted by the model for each of the parameters can be seen in the scatter plots below, 

![AE Results](Autoencoder%20Torch/Complex%20Plane/Results/AE%20Results.png)

The absolute mean error for this model in this case was an average of 8% for all the parameters.

### "CNN FC NN Keras"/"Complex Plane"/AN.ipynb

This is an AlexNet-like implementation that consists of a CNN layer directly connected to a FC layer implemented in Keras.

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a tensor of 2D matrices that represent "images" of the s-plane data of our ladder network circuit. Each image is 100 by 100 pixels in size and has 2 channels. The first channel is the magnitude and the second channel represents the phase of the system. "labels.mat" is a 3D matrix containing vectors of 6 parameters.

The model outputs 6 parameters that each represent a component in the ladder network.

#### Procedure and Results

Two channel data of the appropriate size for the program was generated and inputted. The total size of the dataset is 500 samples, with 300 of them being used for training and the rest are used for testing. The data was generated using matlab (Code will be provided soon).

The results predicted by the model for each of the parameters can be seen in the scatter plots below,

![AN Results](CNN%20FC%20NN%20Keras/Complex%20Plane/Results/AN%20Results.png)

The absolute mean error for each of the parameters in this model' prediction ranged between 61% at the worst and 24% at best. The average error for all parameters was an average of around 30%.

### "CV NN Keras"/"Complex Plane"/"FC NN.ipynb"

This is a fully connected neural network implementation which takes complex valued inputs and uses complex valued weights and biases. It is implemented using the cvnn library.

#### Inputs and Outputs

This implementation takes in two datasets "DS.mat" and "labels.mat". "DS.mat" contains a 3D matrix of complex vectors that contain the locations of poles in our ladder network circuit. Each vector contains 4 poles. labels.mat" is a 3D matrix containing 6 parameter vectors.

The model outputs 6 parameters that each represents a component in the ladder network.

#### Procedure and Results

Pole locations were generated from different ladder networks using matlab. The total size of the data set is 1000 samples, with 800 of them being used for training and the rest are used for testing.

The results predicted by the model for each of the parameters can be seen in the scatter plots below,

![FC NN Results](CV%20NN%20Keras/Complex%20Plane/Results/Results%20FC%20NN.png)

The absolute mean error for each of the parameters in this model ranged between 7% and 9%.