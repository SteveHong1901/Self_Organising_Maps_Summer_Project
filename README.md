# Developing Self-Organising Maps for categorical data

This is a research project conducted with the Mathematics Department at University College London (UCL), supervised by Dr. Ferran Espuny Pujol.

Self-organising map, first developed by Kohonen, is a clustering method that helps to display
very large, high-dimensional datasets in a low-dimensional space. It is a special variation of
unsupervised neural networks, where processing units, or neurons, are arranged in a 2-dimensional
grid and after certain iterations of update, observed data could be projected onto the grid so that
clusters of data can be revealed while preserving the topology of the data set. However, the original
SOM algorithm is only designed for numerical data, which makes it extremely limited for most
datasets nowadays that contains both numerical and categorical data. This research will therefore
investigate the available extensions of the SOM for dealing with categorical data and compare
their effectiveness, then decide the most feasible way to update the weight of the neurons.

The included BatchSom.py file is the current implementation of the batch algorithm of SOM. Further implemation on the categorical data, guided by NCSOM, has been written down in pseudocode, but yet to be implemented due to the time frame of the project. 
