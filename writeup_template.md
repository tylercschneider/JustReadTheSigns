# **JUST READ THE SIGNS** 

## Summary

---
### Data Set Summary & Exploration

German Traffic Sign Data athered from

* Training set has 34,799 images
* Validation set has 12,630 images
* Test set has 12,630 images

* Each image comes in a 32 x 32 x 3 format

* There are 43 different types of signs.

Example Image from DataSet

![alt text][image1]


### Design and Test a Model Architecture

In order to effectively train the model the images need to all be the same size and shape. 
Thankfully this huge dataset has already been partially preprocessed. 
All of the images come in  32 x 32 x 3 format. This reduces a ton of preprocessing headaches. 
This will allow us to pass them into the neural net with minimal processing on our end.

Normalization:

Grey Scale

The dataset could be processed further by taking the existing images from the dataset and augmenting them slightly in order to make them unique enough from there counterparts that dataset would be larger and have even more examples to train on.



#### MODEL ARCHITECHTURE

My final model consisted of the following layers:

| Layer         		|     Description	        					
|:---------------------:|:---------------------------------------------: 
| Input         		| 32x32x1 GreyScale image   						
 
| Convolution 3x3     	| 1x1 stride, same padding, outputs 28x28x6 	
| RELU					|												
| Max pooling	      	| 2x2 stride,  outputs 14x14x6 				

| Convolution 3x3     	| 1x1 stride, same padding, outputs 28x28x6 	
| RELU					|												
| Max pooling	      	| 2x2 stride,  outputs 14x14x6 	

| Convolution 3x3	    | etc.      									
| Fully connected		| etc.        									
| Softmax				| etc.        									
|						|												
|						|												
 

 This architechture could further be improved by adding drop out.


#### 3. Describe how you trained your model. The discussion can include the type of optimizer, the batch size, number of epochs and any hyperparameters such as learning rate.

To train the model, I used an ....

#### 4. Describe the approach taken for finding a solution and getting the validation set accuracy to be at least 0.93. Include in the discussion the results on the training, validation and test sets and where in the code these were calculated. Your approach may have been an iterative process, in which case, outline the steps you took to get to the final solution and why you chose those steps. Perhaps your solution involved an already well known implementation or architecture. In this case, discuss why you think the architecture is suitable for the current problem.

My final model results were:
* validation set accuracy of .924
* test set accuracy of .909
* web photo test set accuracy of .60



* LeNet was used to process these images. It already accepted 32 x 32 x 1 images. It was easy to first edit the model to accept 32 x 32 x 3 but then decided to just to feed it greyscale images and switched it back to 32 x 32 x 1. It definitely performed with a really high accuracy on the different sets of data and the random images I fed it which is covered below. And there is potentially the human error of me misclassifying them and the model actually having guessed them correctly. It wasn't super easy to look up what a random sign was. I don't know the names of signs in the US let alone the names of the diverse set found in Germany.
 

### Testing Model on Images not in DataSet

#### The real litmus test is... Does this work on real images found out in the wild? So I Google searched for German Traffic Signs. Downloaded 5. Tried to figure out what signs they were(as mentioned above I'm not super confident about my ability to identify German signs).

Here they are...

![alt text][image4] ![alt text][image5] ![alt text][image6] 
![alt text][image7] ![alt text][image8]

SideNote: I am really impressed by the image transformation powers of OpenCV. With a single line the randomly sized photo I loaded into the system was transformed into a 32x32x3. There definitely was a bit of squish but overall photo looked the same and it didn't seem to effect the models guesses.


RESULTS

| Image			        |     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| Stop Sign      		| Stop sign   									 
| U-turn     			| U-turn 										
| Yield					| Yield											
| 100 km/h	      		| Bumpy Road					 				
| Slippery Road			| Slippery Road      							


The model was able to correctly guess 3 out of 5 signs, which gives an accuracy of 60%. This really impresses me given that these are wild signs, are heavily edited, and I potentially misclassified them. I feel confident that I guessed at least 3 right if the model agreed with me!


### So the thought process of the model was as follows...


First Sign: 

| Probability         	|     Prediction	        					 
|:---------------------:|:---------------------------------------------: 
| .60         			| Stop sign   								 
| .20     				| U-turn 										
| .05					| Yield											
| .04	      			| Bumpy Road					 			
| .01				    | Slippery Road      							


Second Sign:   

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| .60         			| Stop sign   									 
| .20     				| U-turn 										
| .05					| Yield											
| .04	      			| Bumpy Road					 				
| .01				    | Slippery Road      							

Third Sign:

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| .60         			| Stop sign   									 
| .20     				| U-turn 										
| .05					| Yield											
| .04	      			| Bumpy Road					 				
| .01				    | Slippery Road      							

Fourth Sign:

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| .60         			| Stop sign   									 
| .20     				| U-turn 										
| .05					| Yield											
| .04	      			| Bumpy Road					 				
| .01				    | Slippery Road      							


Fifth Sign:

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| .60         			| Stop sign   									 
| .20     				| U-turn 										
| .05					| Yield											
| .04	      			| Bumpy Road					 				
| .01				    | Slippery Road      							

### Awesome Stuff :)