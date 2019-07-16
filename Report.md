[image1]: example.png "Trained Agent"
[image2]: data_exploration.png "data_exploration"
This report come as part of the Udacity Nanodegree on Self Driving Car Engineering.

### Introduction
In this Project, we will try to sort the German Traffic Signs from [this](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/traffic-signs-data.zip) database using a Convolutional Neural Network.



### Description

In order to be able to give any image of a traffic sign to our network and hopefully have a good prediction, we will procede this three main parts of the code:

* Load the Data and explore it
* Design and Test a Model Architecture
* Test our Model on New Images

All the code for each step of this algorithm is contained in the `Traffic_Sign_Classifier.ipynb` Notebook. We'll go through every step one by one.

1. Load the Data and explore it

In this first part, we first load the data form the pickle files then we explore it randomly in order to see what it looks like and to verify that the label are well implemented. In order to do that, I wrote all the label in the 'sign' list to be able to directly write the traffic sign label on top of each image as we can see below:

![data_exploration][image2] 

2. Design and Test a Model Architecture

In this section, we begin by processing the data. The size of each image is already (32*32) but in order to have a simpler and effective Neural Network, we gray_scal our images and then we normalize each of their pixels with the formula: x=(x-128)/128.

Then we choose to modify the LeNet() model for our neural network in order to have better results with our data. For example here, we decide to have nine and the 21 of depth for the first and second convolutional layer. We also improved the number of weight of the fully connected layer and decided to add a 4th one.

With this modifications, we tuned the parameters as follow:

*Learning_rate = 0.001
*EPOCHS = 20
*BATCH_SIZE = 128

and obtain an accuracy of 0.95 for the validation data.

3. Test our Model on New Images

Finally, in order to understand better the model and to be sure that it will work with real pictures, we choose 5 pictures of german traffic signs on the internet, resize them, rescale them, gray_scale them and normalize them and we obtain the following results:

![Traffic Sign Example][image1] 

As you can see here the model had a good prediction for 4 out of 5 images wich is a good beginning but show that improvement is still needed.

### Reflexion

Now that our model works pretty well for a majority of image, we have to do the hardest work which is to reach for the last 5-10% of good prediction. 

I think there are at least 2 main points on which we could improve the efficience of the algorithm:

- At first, We could try to have a better processing of our data, which mean that we could for example add noise or gaussian_blur on our inputs image, or feed the model with the RGB color space.
  - Finally, using the Keras environment, we could have a simpler implementation of our model and then it would be easier to find a better model four our data classification.







