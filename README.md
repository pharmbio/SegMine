# SegMine
Playground for Segmentation and Data-mining. This repository contains the necessary metadata and images to perform a simple image-segmentation of CellPainting images of U2OS cells. It also contains an simple assignment for making a pipeline

#### Assignment
##### Background
Large scale microscopy-based experiments are typically performed in multiwell plates. In each of the wells, cells are treated with a perturbant (chemical, genetic or biologic) and high content bioimage analysis is performed to transform the images into numbers in order to quantify measurable differences among the treatments. Typically, negative and positive controls, that is, conditions in which the cells are not expected to change or are expected to change, respectively, are used. In a multiplex microscopy assay high content experiment, the raw data consists of images in multiple channels, each stack corresponding to a specific combination of well, z-plane, and site.

One important step is to detect objects of interest, in this case cells, and segment them in order to subsequently extract morphological (numerical) information. This can be done in multiple ways, though for this assignment we will focus on using deep-learning - an approach that has proven to be quite effective. An example of a tool that can do this is Cellpose (https://github.com/MouseLand/cellpose). There are multiple tools that can do this, one such tool is DeepProfiler (https://github.com/cytomining/DeepProfiler). This will segment cells and provide a cell mask, which can then be used to harvest cells from the data for future analysis.

Another important step is to mine tabular data from the images, in order to construct a vectorized representation of what happens in the image - this can be done either by measuring specific parts of the image (as done by CellProfiler) or mining the data by embedding it and processing it through a model (as is the case with DeepProfiler). 

Regardless of which method, the result is  tabular data that can be further analyzed with a multitude of models - both supervised and unsupervised. A widely used set of unsupervised models would be Principal Component Analysis (PCA), T-Distributed Stochastic Neighbor Embedding( t-SNE), and Uniform Manifold Projection (UMAP).

With this in mind, we will ask you to provide a quick exploratory analysis of a reduced dataset containing cell painting images.The images in the dataset have untreated wells (DMSO, a negative control), and wells treated with reference substances (Positive controls) - see the metadata in 'data/plate_metadata.csv'. The metadata is stored in a Dataframe, each row corresponding to a single well-site-plane combination, and what treatment (if any!) that well has. The data is located in 'data/images/'

##### You will now implement in python a Pipeline to:
Segment the cells into single-cell masks.
Harvest the cells
Calculate the location of each cell
Mine profiles for each cell
Aggregate the data as either the Mean or Median of each unique well-site combo
Cluster the data using either UMAP or TSNE

Additionally, we want you to create a public git-repository with your solutions and output plots, where you provide your pipeline example code as one of either:
A set of *.py scripts with a config-file
A set of jupyter-notebooks
And your solution needs to be executable in a *nix environment (primarily Linux). Hint - WSL provides compatibility in Windows, and MacOS is very similar to Linux when it comes to Python and File-structures.
