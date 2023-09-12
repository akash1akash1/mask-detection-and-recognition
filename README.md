# mask-detection-and-recognition
This code will not run google colab 
run the code in VS Code or jupyter notebook 

#dataset details 
![image](https://github.com/akash1akash1/mask-detection-and-recognition/assets/128292061/1621219a-e950-4edf-80d1-727ffe2bdded)

# Methodology
The first step is to create a dataset and process the images in it.For image processing, we are
using OpenCv -python. It is an open source library used for image processing and computer
vision tasks. It is used for face detection, which we are interested in. So, install opencv
-python and import cv2.
The next task would be to select the important areas for the dataset and process them. We are
using a webcam to take the images. We have also collected the pictures from a google form,
and process this raw image data to get the region of interest(roi) of the image, only face data.
We can manually take these pictures from the webcam inorder to capture the face data.
Because, we are interested in only the face of the person and nothing else, so the target of the
image is only captured, processed and stored in the local folder. Once the picture is captured,
since the picture might contain some extra information,we need to crop and clean the image
as per our requirement. To do so, we use the cascade classifier function, the haar-cascade() in
order to detect the object. We already have face detection, eye detection and smile detection
xml files available in openCV. So we directly use those files in our project to detect the
targeted components of the image. A picture might contain more than one targeted attribute,
in order to capture them, we are setting the minimum neighbors as 5, so that it can capture at
least 5 faces in a picture and then scaling the picture as per the need. After detecting the
objects, we might get different sizes of the targeted sub-image. In order to process those
different sizes, we use detect_ multiscale function. The output for this function will be the
array of image.We can see the output of this by taking various values and applying
rectangle() on it. This will show the image where the target is detected and drawn with a
rectangle. This is all done using detect multiscale only.Now we can store these images in the
local folder. while capturing the images only we have given the output path as masked or
unmasked and then storing it in the local folder. Like, with a mask –“1” and without a mask
–“0”. So two separate folders are created. Now, we are done with the creation of the dataset.
Proceeding to image processing and training.
Now,we will be taking the cropped image where the targets are specified. To proceed further,
we are checking if there are two eyes in the image otherwise reject the image. if the images
have noise then the unwanted image can be captured, so be manually check the cropped
image and do cleaning as required. The size of the cropped image is also different for all
images so we are also resizing these cropped images while adding all of them to a separate
dataset array. Elaborating this point. Since all the images will not have a specific or common
dimension after cropping, we set the images to a specific dimension. Here we used 50x50.
We already have two classes 0(unmasked) and 1(masked) which are stored separately in the
local folder. Now we combine both these classes and store them in array format. We split this
array for training and testing the model. We used a 70:30 split.Its clear that we need to use
classification algorithms, since the output is categorical. So we performed the most popular
classification algorithms like KNN, SVM, Decision tree, Naive Bayes, and Logistic
Regression. We calculated the Accuracy Score, F1 score, Recall and precision. Based on
Accuracy, which model gives the best results is chosen
