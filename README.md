PROJECT
---
Just Read the Signs - UDACITY Self Driving Car Engineer


DEVELOPER CONTACT
---
[msg me](https://www.linkedin.com/in/tylercschneider "Linkedin")


BUILD TOOLS
---
[Environment used to build](https://github.com/udacity/CarND-Term1-Starter-Kit.git)

HIGHLIGHTS
..* Python 3
..* Open CV


To RUN
---
1. Download the environment, the github link above has detailed directions
2. Open and run code in jupyter notebook.
3. Takes traffic sign as input.
4. Predicts which traffic sign against trained model.

CALCULATIONS
---
Uses Neural Nets to understand what traffic sign it is looking at.

Takes in German Traffic Sign Dataset.

Dataset is presplit into 3 datasets (train, validate, test)

Before running data through model images are preprocessed.

Each one is converted to...
 - Greyscale
 - Normalized

Runs Training Set Thru LeNet convolution neural network
Checks the models accuracy using the Validation Set

After quality accuracy is obtained from Training, model is run on test set to ensure that it is not overfitting and just learning the training set.


Finally test on images from the web that are not part of the pre built datasets. Must be 1 of the 43 german traffic signs that the model has been trained on. 










