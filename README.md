PROJECT
---
Basic Robot Vision - UDACITY Self Driving Car Engineer P1


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
2. Open run code in jupyter notebook.
3. You images within file to see how it works.
4. Predicts and overlays lane lines on single images or every frame in a video it is passed.

CALCULATIONS
---
Uses very rudimentary computer vision techniques.
Passes an image
Converts to grayscale
Smoothes with Gaussian
Finds Gradients with Canny
Removes sections of the image that are unimportant with a mask
Finds what gradients are significant in terms of forming longer lines using Hough equation
Draws predicted lane lines using draw lines function. It calculates the predicted slope and x values associated with fixed y dimensions.

Takes original image and overlays predicted lane lines on it.

Repeats over in over to process a video file.










