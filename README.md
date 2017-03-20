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


