# ElevationGAN
A Machine Learning model which can produce elevation data (create a terrain map) of a 20km area. Trained on real Earth data.

## Important
*This code is still in development and may not work properly.*
*It has only been tested on a single GPU P100 in Kaggle.*
*Tensorboard will not log losses when using TPU (only use TPU for final train)*

## Modes of Use
*At the top of the notebook, there are several variables which can change how the code runs. Most notably, there are three modes to pick from:*

**1. Mode 0 (Optimising Parameters)**

 When using this mode, you can input an array of parameters for the generator and discriminator. The code will then train the model multiple times on these parameters and record the loss via tensorboard. It is up to you to anylise the loss and decide on the best parameters.
 
 **2. Mode 1 (Fully Training Model)**
 
 When using this mode, the model will be trained once using the first set of parameters in the arrays. Loss will be logged via tensorboard *(unless you are using TPU)*.
 
 **3. Mode 3 (Gather Training Data)**
 
 This mode does not train the models, but instead collects the training data based on the defined parameters at the top. It will create and save numpy arrays containing the number of samples specified of 20km squared areas of real Earth elevation data. These arrays are scaled to 640 by 640 giving a resolution of approximately 30m. 

## Training Data
*The training dataset can be downloaded from kaggle via this link [www.kaggle.com/datasets/solveitplanet/elevationdataset](http://).*

## Downloading Tensorboard Logs
*Tensorboard will not output loss when running on TPU because storage buckets are not currently supported*

### On Windows 10 *(Will probably work on windows 11)
1. Download .zip file which is automatically created
2. Extract .zip file in desired location
3. Open command line
4. Run command: tensorboard --logdir=logs --host=localhost  *(Where logs is the file location of the extracted file)*
5. Open browser and type on the address: localhost:6006

Steps for non-windows systems are similiar
