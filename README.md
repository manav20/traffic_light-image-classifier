# Traffic Light Image Classifier
This project implements various computer vision techniques to biuld a classifier from images of traffic lights.The pipeline for the same as follows:
1. Loading and Visualizing the data
2. Pre-Processing
3. Feature Extraction
4. Classfication and Error Visualization
5. Model Evaluation </br> </br>
![](images/all_lights.png)
### 1. Loading and Visualizing the Dataset
This traffic light dataset consists of 1484 number of color images in 3 categories - red, yellow, and green. As with most human-sourced data, the data is not evenly distributed among the types. There are: </br>
* 904 red traffic light images
* 536 green traffic light images
* 44 yellow traffic light images
_All images come from the MIT self-driving car course_
### 2. Pre-Processing
#### Input:
This step ensures that every image is in the same format, of the same size and so on. This is important to ensure that similar images create similar features. All images were trimmed from the sides and the size was fixed to a 32x32 image. A 'Standardized List' was generated for the next steps.
#### Output:
The classifier out is a one-hot encoded label, A red light is labelled as [1, 0, 0],  yellow as: [0, 1, 0] and green as: [0, 0, 1]. 
<!--- Add orignal to standardize tranformation --->
### 3. Feature Extraction
We mainly implement two features in conjuction. First the images are cropped in three equal parts height-wise. Each of theese sub-images are then converted from rgb to hsv space. Average value of saturation is then computed over the 'S' channel and threshold is used to classify into red, yellow and green. The cropping strategy ensures that even if there are miss classification no red light ever gets classified as green since that would be the worst from the autonomous car standpoint.
### 4. Classification and Error Visualization
The feature extraction code is run over the 'Standardized Images' from test dataset. The generated label is compared with the actual label and all the missclassified images are displayed.
### 5. Model Evaluation
The model accuracy is found as 96.296 %
