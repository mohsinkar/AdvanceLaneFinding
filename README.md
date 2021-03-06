## Advanced Lane Finding
In this project, your goal is to write a software pipeline to identify the lane boundaries in a video.

### Processing Steps:
---
The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.


### Camera Calibration

The images captured by the camera lense are somtimes distorted. This could be a problem when detecting the lane lines and trying to keep the car within lanes.

Calculated the camera calibration matrix and distortion coefficients


![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Camera%20Calibration/Image_1.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Camera%20Calibration/Image_2.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Camera%20Calibration/Image_3.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Camera%20Calibration/Image_4.png)

Using the calibration matrix and the distotion coefficients corrected the images distortion on the test image set to make sure the following step of the pipeline is working as expected.

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Images%20Undistorted/Images_1.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Images%20Undistorted/Images_2.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Images%20Undistorted/Images_3.png)

## Image Transformation

After defining the region of interest and the source and distination points the image was transformed to look at the street lines as Birds eye view

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Perspective%20Transform/Image_1.png)

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Perspective%20Transform/Image_2.png)


## Gradient Transformation:

1. HSV
2. Sobel
3. Color range for yellow and white 
      color_ranges_white = [([0,0,255-sensitivity],[255,sensitivity,255]) ]    
      color_ranges_yellow = [([5,100,100],[25,255,255])]
      
![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Gradient%20Threshold/Image_1.png)
![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Gradient%20Threshold/Image_2.png)

## Left and Right Lane Detection

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Lane%20Detection/Image_1.png)
![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Lane%20Detection/Image_2.png)

## Calculating the curvature and Tranforming back

![Alt text](https://github.com/mohsinkar/AdvanceLaneFinding/blob/master/Radius%20and%20Curvature/Image_1.png)


## Current Issues and Improvements:

* There are a few issues that can be fixed on detecting lane better under the Shadow and changing street color under shade and sunlight.

* More different color can be detected to better find the lanes by adjusting and playing arund the sensitivity of the ranges.
     color_ranges_white = [([0,0,255-sensitivity],[255,sensitivity,255]) ]    
     color_ranges_yellow = [([5,100,100],[25,255,255])]

* Also one potential thing that can be done to improve is to better average out the curve based on previous frames and perform strict sanity checks.

