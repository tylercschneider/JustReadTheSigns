# JUST READ THE SIGNS
---
### Data Set Summary & Exploration

German Traffic Sign Data athered from

* Training set has 34,799 images
* Validation set has 12,630 images
* Test set has 12,630 images

* Each image comes in a 32 x 32 x 3 format

* There are 43 different types of signs.

Example Image from DataSet

<img src="dataphoto.png" alt="dataphoto" width="214px"/>


### Design and Test a Model Architecture

In order to effectively train the model the images need to all be the same size and shape. 
Thankfully this huge dataset has already been partially preprocessed. 
All of the images come in  32 x 32 x 3 format. This reduces a ton of preprocessing headaches. 
This will allow us to pass them into the neural net with minimal processing on our end.

With Numpy Array and math...
 - Grey Scale: Sum of RGB/3 

 - Normalize: (Each pixel-128)/128
 

The dataset could be processed further by taking the existing images from the dataset and augmenting them slightly in order to make them unique enough from there counterparts that dataset would be larger and have even more examples to train on.



### MODEL ARCHITECHTURE

My final model consisted of the following layers:

|          			|     Description	        					
|:---------------------:|:---------------------------------------------: 
| LAYER 1 |
| Input      		| 32x32x1 GreyScale image   			
| Convolution 3x3     	| 1x1 stride, Valid padding, Outputs 28x28x6 	
| RELU					|												
| Max pooling	      	| 2x2 stride, Valid padding, Outputs 14x14x6 				
||
| LAYER 2|
| Convolution 3x3     	| 1x1 stride, Valid padding, Outputs 28x28x6 	
| RELU					|												
| Max pooling	      	| 2x2 stride, Valid padding, Outputs 14x14x6 	
| Flatten | Outputs 400
||
| LAYER 3|
| Fully Connected	    | Outputs 120 
| RELU |     						
||
| LAYER 4|
| Fully connected		| Outputs 84       					
| RELU				|       								
||
| LAYER 5|	
| Fully connected		| Outputs 43        						
									
 

 This architechture could further be improved by adding drop out.
 The training could be further improved by running for more than 10 epochs.

### TRAINING

To train the model, I used a LeNet with the following HyperParameters....

 - Epochs : 10
 - Batch Size : 128
 - Learn Rate : .001
 - Optimizer : Adam

### METHODOLOGY

My final model accuracies:
* validation : .93
* test : .91
* web : .60

LeNet was used to process these images. It already accepted 32 x 32 x 1 images. It was easy to first edit the model to accept 32 x 32 x 3 but then decided to just to feed it greyscale images and switched it back to 32 x 32 x 1. It definitely performed with a really high accuracy on the different sets of data and the random images I fed it which is covered below. And there is potentially the human error of me misclassifying them and the model actually having guessed them correctly. It wasn't super easy to look up what a random sign was. I don't know the names of signs in the US let alone the names of the diverse set found in Germany.
 

### LITMUS TEST - images from outside of dataset

I googled German Traffic Signs. Downloaded 5. Tried to figure out what signs they were(as mentioned above I'm not super confident about my ability to identify German signs).

Here they are...

<img src="1.jpg" alt="Speed Limit" width="214px"/>
<img src="2.jpg" alt="Keep Right" width="214px"/>
<img src="3.jpg" alt="No Passing" width="214px"/>
<img src="4.jpg" alt="Road Work" width="214px"/>
<img src="5.jpg" alt="No Entry" width="214px"/>


SideNote: I am really impressed by the image transformation powers of OpenCV. With a single line the randomly sized photo I loaded into the system was transformed into a 32x32x3. There definitely was a bit of squish but overall photo looked the same and it didn't seem to effect the models guesses.


RESULTS

| Image			        |     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| Speed Limit 30      		| Speed Limit 30  									 
| Keep Right     			| Priority Road										
| No Passing			| Go Straight Or Left										
| Road Work      		| Road Work					 				
| No Entry		| No Entry      							


The model was able to correctly guess 3 out of 5 signs, which gives an accuracy of 60%. This really impresses me given that these are wild signs, are heavily edited, and I potentially misclassified them. I feel confident that I guessed at least 3 right if the model agreed with me!


### So the thought process of the model was as follows...


First Sign: Speed Limit 30

| Probability         	|     Prediction	        					 
|:---------------------:|:---------------------------------------------: 
| .999         			| Speed Limit 30   								 
| .001    				| Speed Limit 20										
| .001					| Wild Animals Crossing											
| .00     			| Roundabout Mandatory					 			
| .00				    | Speed Limit 50      							


Second Sign: Keep Right

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
 .995         			| Priority Road   									 
| .005     				| No Passing										
| .00					| Slippery Road											
| .00	      			| Vehicles over 3.5 metric tons prohibited					 				
| .00			    | No passing for vehicles over 3.5 metric tons     							


Third Sign: No Passing

| Probability         	|     Prediction	        					
|:-------------------:|:---------------------------------------------: 
| .969        			| Go straight or left   									 
| .025     				| Roundabout mandatory										
| .006					| Traffic signals											
| .00	      			| Priority Road					 				
| .00				    | Road narrows on the right      							


Fourth Sign: Road Work

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
| 1.00         			| Road Work   									 
| .00    				| Right-of-way at the next intersection 										
| .00					| Dangerous curve to the left										
| .00	      			| Double curve					 				
| .00				    | Speed limit 30    							


Fifth Sign: No Entry

| Probability         	|     Prediction	        					
|:---------------------:|:---------------------------------------------: 
|  1.00         		| No Entry 									 
| .00    				| Stop 										
| .00					| Priority road										
| .00	      			| No passing					 				
| .00    				| Speed Limit 20

### Awesome Stuff :)