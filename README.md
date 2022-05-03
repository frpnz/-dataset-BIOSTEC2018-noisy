The dataset is made up of three classes of interest:

Cancer (AC) - label 0
Adenoma (AD), a lesion that may turn into cancer - label 1
Healthy tissue (H) - - label 2

And four classes of spurious images, associated with a fake class from AC, AD, H:

Blood (BLOOD)
Fat (FAT) 
Glass (GLASS)
Stroma (STROMA)

Refer to this paper for a fully description of the dataset:

F. Ponzio, G. Deodato, E. Macii, S. Di Cataldo and E. Ficarra, "Exploiting “Uncertain” Deep Networks for Data Cleaning in Digital Pathology," 2020 IEEE 17th International Symposium on Biomedical Imaging (ISBI), Iowa City, IA, USA, 2020, pp. 1139-1143, doi: 10.1109/ISBI45749.2020.9098605.

The images are in form of numpy array:

• X{train, test}.npy
shape ({12336, 7308}, 32, 32, 3)
training images

• patients{train, test}.npy
shape ({12336, 7308},)
patients corresponding to {train, test} images

• real_classes{train, test}.npy
shape ({12336, 7308},)
real class corresponding to {train, test} images

• Y{train, test}.npy
shape ({12336, 7308},)
labels corresponding to {train, test} images. In case of spurious image this is a
“fake” class belonging to [AC, AD, H]

X_train and X_test are zero-centered and normalized over 255

X_train_norm = (X_train - mean_x_train) / 255
X_test_norm = (X_test - mean_x_train) / 255

mean_x_train.npy is the training set mean for datasets zero-centering


