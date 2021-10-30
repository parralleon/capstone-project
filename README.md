# A Limit Order Book based Deep Learning Model for Cryptocurrency Price Trend Prediction
This repository is created to hold all code generated from the final capstone project on the MScFE from World Quant University. The intention of this project is
to create a deep learning model for the mid-price movement prediction task on cryptocurrency markets. Four jupyter notebook files are provided: 0. Limit_Order_Book_Reconstruction, 1. data_preprocessing, 2. creating_sequences_and_labeling and 3. training. A brief description of each is provided below.

## 0. Limit_Order_Book_Reconstruction

Under this notebook file, the code to reconstruct the Limit Order Book out of raw event messages and a snapshot is provided. Just the first 10 levels of each side of the book are stored, however, the code can be adapted to any number of levels as desired. For this project, just 10 levels were used. Final reconstructed files are hdf5 files.

## 1. data_preprocessing

A new method for scaling the data is contained on this notebook. It takes the reconstructed LOB and a apply a individual scaling per example, then, a z-score normalization is applied on the scaled data.

## 2. creating_sequences_and_labeling

This piece of code allows to roll a window on the LOB time series data in order to construct sequences of a determined length, for this project a length of 100 consecutive events was chosen. No overlapping exist between sequences, however, length and overlapping of a sequence could be adapted as well. Labels are created for each of the sequences, the Triple Barrier Method suggested by Marcos Lopez de Prado is implemented. A sequence of eventes is labeled as: Up, Down or Stationary. The balance of each the classes are determined by a threshold value \alpha.

## 3. training

Under this notebook, the LSTM model architecture is created, as well as the datasets (training, validation and test sets) are loaded. At the end of the training, the model is evaluated on the test set for final metrics report.

# Installation Requirements Notes:

The following libraries are needed in order to run the above notebooks, please make sure such libraries are installed prior running the files.

- Pytorch
- Numpy
- Datetime
- Scikit-learn
- Matplotlib
- Pandas
- JSON
- H5py
- OS

If any is missing please refer to the installation process on the official website library.

