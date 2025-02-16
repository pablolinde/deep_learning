In this notebook, proteins are classified using a CNN.

The data to be processed consist of a set of synthetic cryo-EM images. Each image contains a 2D projection of an instance of a particular molecular complex in a random orientation. Specifically, there are five classes, as indicated by their codes in the Protein Data Bank [PDB](https://www.rcsb.org/):

1. [3j9i](https://www.rcsb.org/structure/3J9I)
2. [4cr2](https://www.rcsb.org/structure/4CR2)
3. [4v4r](https://www.rcsb.org/structure/4V4R)
4. [4v94](https://www.rcsb.org/structure/4V94)
5. [6utj](https://www.rcsb.org/structure/6UTJ)

The images are 50x50 pixels and are stored in PNG files. The file names determine the class name, the class identifier, and the particle number for that class. The dataset is located in the directory *imgs/SNR_high*.

To train the model, it is necessary to load the images from disk and convert them into tensors. The class labels for each image can be extracted from the file names. As the images might be read sequentially by class—which could distort the training—it is recommended to randomize their order using the functionality provided by Python's scikit-learn machine learning package.
"""
