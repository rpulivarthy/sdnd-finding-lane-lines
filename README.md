# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project you will detect lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

Creating a Great Writeup
---
For this project, a great writeup should provide a detailed response to the "Reflection" section of the [project rubric](https://review.udacity.com/#!/rubrics/322/view). There are three parts to the reflection:

Files Included

1. P1.ipynb </br>
2. test_images_output/* </br>
    Processed Test images </br>
3. test_videos_output/* </br>
    Processed videos 
</br>

Describe the pipeline
    1. Select White and Yellow lines </br>
        The test images that are provided contain both white and yellow. </br>
        White Lanes </br>
        ![alt-text](./test_images/solidWhiteCurve.jpg)</br>
        Yellow Lanes</br>
        ![alt-text](./test_images/solidYellowCurve.jpg)</br>
    2. Apply Gray Scale </br>
        This is needed for canny to properly detect edges </br>
    3. Apply Gaussian Smooting </br>
        Apply Gaussian Smoothing for the edges</br>
    4. Apply Canny </br>
        Detect the edges </br>
    5. Apply Hough transform after canny. </br>
        All the edges will result in lines in parameter space. The point of intersect in the hough transform is the line in 
        image space with slope and constant
    6. Draw the lane lines </br>
        The lines from the hough are fed to this function. 
        Average slope intercept is derived from multiple lines.
        Lanes and drawn on the original image
         White Lanes</br>
        ![alt-text](./test_images_output/solidWhiteCurve.jpg)</br>
        Yellow Lanes</br>
        ![alt-text](./test_images_output/solidYellowCurve.jpg)</br>

Link to Videos </br>
[White Lanes](https://youtu.be/Xv-tLLH5GOw)

[Yellow Lanes](https://youtu.be/xZGnnONLlWY)

2. Identify any shortcomings
    1. Curvature of the road is not considered.
</br>
3. Reflection:
    The current pipeline works in detecting the images with standard slopes more like straight lines. 
    The current pipeline will fail on the turning roads.  
    


