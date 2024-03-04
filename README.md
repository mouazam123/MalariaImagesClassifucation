
#### The original data used in our study contains 33,007 images.

#### In the Preprocessing_method.ipynb file: the first step of our work is to create pre-processed data using the Canny filter and cropping method from the original data.

First of all, the original data directory (OriginalData) contains two folders: train (containing training data) and test (containing test data).

* In the train folder, we have two subfolders, Parasitized (containing 23207 infected images) and Uninfected (containing 23200 uninfected images).

* In the test folder, we have two subfolders, Parasitized(containing 3300 infected images) and Uninfected (containing 3300 uninfected images).

We've created a directory named CannyData, which reproduces the folder and subfolder structure of the OriginalData directory, but is empty.

The procedure consists in creating a source path to a subfolder of the OriginalData directory and a destination path to a subfolder of the CannyData directory.

The procedure consists in creating a source path to a subfolder of the OriginalData directory and a destination path to a subfolder of the CannyData directory.

Each time, the source path points to a subfolder that is homologous to the subfolder pointed to by the destination path.

We have four source subfolders in the OriginalData directory and four destination subfolders in the CannyData directory.

The paths to the four source subfolders (OriginalData directory) and the paths to their homologous destination subfolders (CannyData directory) are given below.

Source1 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/OriginalData/train/
Parasitized')

print(len(os.listdir(source1)))

destestination1 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/CannyData/train/
Parasitized')
print(len(os.listdir(destestination1)))

source2 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/OriginalData/train/ Uninfected')

print(len(os.listdir(source2)))

destestination2 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/CannyData/train/ Uninfected')

print(len(os.listdir(destestination2))

source3 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/OriginalData/test/
Parasitized')

print(len(os.listdir(source3)))

destestination3 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/CannyData/test/
Parasitized')

print(len(os.listdir(destestination3)))

source4 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/OriginalData/test/ Uninfected')

print(len(os.listdir(source4)))

destestination4 = os.path.join('/content/drive/MyDrive/Our_Data/Thesis/LargeData/CannyData/test/ Uninfected')

print(len(os.listdir(destestination4))

Then we created a loop that takes the images one by one from a subfolder of the source directory (OriginalData), preprocesses them with the Canny filter and saves them in the homologous subfolder of the destination directory (CannyData).

We do the same with all subfolders in the OriginalData directory that are homologous to subfolders in the CannyData directory.

 To obtain the data set pre-processed with the cropping method, we created the ScroppedData directory with the same folders and subfolders as the OriginalData directory, which are also empty, and then followed the same procedure used to obtain the data in the CannyData directory.

At level, the source directory is the same (OriginalData), but the destination directory is ScroppedData and the pre-processing method here is the image cropping method.

### Model training

To train the models in each of these files CNN.ipynb, Dense_Net.ipynb and LeNet.ipynb, we used data from the CannyData directory to evaluate the results found with the pre-processing method using the Canny filter and then used data from the ScroppedData directory to evaluate the results found with the pre-processing method using cropping method.

### Calculation of performance metrics 

To determine the performance metrics for each model, we used the test data specific to the data used to train the model to find the values for true positives, false negatives, true negatives and false positives.
These values were used to calculate the values of performance metrics such as Accuracy, Sensitivity (Recall), Specificity, Precision, F1 Score and Matthews Correlation Coefficient (MCC).



