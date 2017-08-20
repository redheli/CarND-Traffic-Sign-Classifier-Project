# **Traffic Sign Recognition**

---
### Writeup


link to my [project code](https://github.com/redheli/CarND-Traffic-Sign-Classifier-Project/blob/master/Traffic_Sign_Classifier.ipynb)

### Data Set Summary & Exploration

#### Train and test dataset download from http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset

signs data set:

* The size of training set is 31367
* The size of the validation set is 7842
* The size of test set is 12630
* The shape of a traffic sign image is not 32x32x3
* The number of unique classes/labels in the data set is 43

I use pillow to resize the images to 32x32x3

#### visualization of the dataset.

Yield
<img src="Yield.png" width="480"  />

histogram for the distribution
<img src="hits.png" width="480"  />


### Design and Test a Model Architecture

#### 1. Normalizes the data between 0.1 and 0.9 instead of 0 to 255

```
def normalize(data):
    return data / 255 * 0.8 + 0.1
```

I normalized the image data because it makes training easy.

I did not grayscale the images, as color is important feature.


#### 2. final model architecture

My final model consisted of the following layers:

<img src="lll.png" width="480"  />



#### 3. Train model

To train the model, I used tensorflow AdamOptimizer,learning rate 0.0009, EPOCHS = 30
BATCH_SIZE = 256.




#### 4. Increase the epochs, I get better training accuracy 0.99.
Of course I modified the model layer to from original LeNet-5 to currenr structure.



My final model results were:
* training set accuracy of 0.999
* validation set accuracy of 0.93
* test set accuracy of 0.942


###Test a Model on New Images

####1. Choose five German traffic signs found on the web and provide them in the report. For each image, discuss what quality or qualities might be difficult to classify.

Here are five German traffic signs that I found on the web:

<img src="custom/example_00005.png" width="200"  />
<img src="custom/example_00007.png" width="200"  />
<img src="custom/example_00008.png" width="200"  />
<img src="custom/example_00030.png" width="200"  />
<img src="custom/example_00035.png" width="200"  />


####2. model's predictions

**I got 100% accuracy!!!!**

Here are the results of the prediction:

| Image			        |     Prediction	        					|
|:---------------------:|:---------------------------------------------:|
| Stop Sign      		| Stop sign   									|
| Keep left     			| Keep left 										|
| Roundabout mandatory					| Roundabout mandatory											|
| Children crossing| Children crossing|
| Speed limit (20km/h)			| Speed limit (20km/h)     							|
