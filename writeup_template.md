#**Traffic Sign Recognition** 

---

**Build a Traffic Sign Recognition Project**




You're reading it! and here is a link to my 
https://github.com/Ilkka-AI/Self-driving-car-Traffic-sign-classification

All generated figures are provided in the notebook and the html.

###Data Set Summary & Exploration

####1. 

The code for this step is contained in the second code cell of the IPython notebook.  

I used the pandas library to calculate summary statistics of the traffic signs data set:

* The size of training set is 34799 
* The size of the final test set is 12630
* The size of the validation set is 4410
* The shape of a traffic sign image is 32x32x3
* The number of unique classes/labels in the data set is 43

####2. 
An exploratory visualization is provided in the notebook. 

####1. 
For pre-processing I normalized each color channel in the images to the scale between 0 and 1. I used a function normalize_grayscale provided in the course material, however, I applied it to all 3 channels. 

####2. 
I did not use cross-validation and didn't understand why this would really be necessary. The original data set came with three files, training, validation and test set. I only used those sets to save time in an already time-consuming project. 


####3

I extended the LeNet by doubling all layer depths,adding one more convolutional layer and to the later part an additional fully connected layer. I also included dropout in the second last layer. 

Conv 1 28x28x12
Relu 
Pooling 1 14x14x12
Conv 2 10x10x32
Relu
Conv 3 10x10x64
Relu
Pooling 2 5x5x64
Full 1 3200x240
Relu
Full 2 240x168
Relu
dropout
Output 168,10

The code for my final model is located in the fifth cell of the ipython notebook. 


####4. 

The code for training the model is located in the sixth cell of the ipython notebook. 

To train the model, I used the procedure developed in the LeNet code. I used a batch size of 128, 40 epochs, learning rate 0.001.

####5. Describe the approach taken for finding a solution. 


My final model results were:
* training set accuracy of 0.999
* validation set accuracy of 0.951
* test set accuracy of 0.933

An iterative approach was chosen:
I started with the LeNet architecture and increased the layer depths and added additional layers. These resulted in an observation of an increased prediction accuracy; the rational is simply that a lot more nodes enables the model to learn more complicated patters as traffic signs are more complicated than grayscale hand-written digits. When the model got larger, I added a dropout to decrease overfitting. The model learns the training set almost perfectly but also generalized well to the validation and test sets. With limited time to invest in this project, I couldn't try more sophisticated approaches.

 

###Test a Model on New Images

####1. Choose five German traffic signs found on the web and provide them in the report. For each image, discuss what quality or qualities might be difficult to classify.

6 images were downloaded. I don't see any reason why their classification prospects should differ from the training set. 

####2. 

For the new images 5 out of 6 were correctly classified. The accuracy 0.83 is comparable to the test set, subject to uncertainty due to small sample size. The road work sign was confused with beware bikes and beware children signs that look quite similar having only the inner structure different.   

      							|

####3. The model is very certain >0.99 about all its 6 predictions, giving only marginal probability for the other options. See numbers in notebook. 

Visualizing the featuremaps shows that the model finds relevant patterns for each test images. 




 