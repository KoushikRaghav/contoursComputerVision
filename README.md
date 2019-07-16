# contoursComputerVision

## What are contours?

Contours can be explained simply as a curve joining all the continuous points (along the boundary), having same color or intensity. The contours are a useful tool for shape analysis and object detection and recognition.

For better accuracy, use binary images. So before finding contours, apply threshold or canny edge detection.

In OpenCV, finding contours is like finding white object from black background. So remember, object to be found should be white and background should be black.

## How to draw the contours?

To draw the contours, cv.drawContours() function is used. It can also be used to draw any shape provided you have its boundary points. Its first argument is source image, second argument is the contours which should be passed as a Python list, third argument is index of contours (useful when drawing individual contour. To draw all contours, pass -1) and remaining arguments are color, thickness etc.



The main difference is in the hierarchy that is returned (giving the relationship between one contour and the next).

#### 1. CV_RETR_EXTERNAL 
   Gives "outer" contours, so if you have (say) one contour enclosing another (like concentric circles), only 
the outermost is given.

#### 2. CV_RETR_LIST 
   Gives all the contours and doesn't even bother calculating the hierarchy -- good if you only want the contours 
and don't care whether one is nested inside another.

#### 3. CV_RETR_CCOMP 
   Gives contours and organises them into outer and inner contours. Every contour is either the outline of an 
object, or the outline of an object inside another object (i.e. hole). The hierarchy is adjusted accordingly. This can be 
useful if (say) you want to find all holes.

#### 4. CV_RETR_TREE 
   Calculates the full hierarchy of the contours. So you can say that object1 is nested 4 levels deep within 
object2 and object3 is also nested 4 levels deep.



## Canny Edge Detection

    Noise Reduction
    Finding Intensity Gradient of the Image
    Non-maximum Suppression
    Hysteresis Thresholding
