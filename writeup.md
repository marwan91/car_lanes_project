**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



---

### Reflection

### 1. Pipeline Description

My pipeline can be divided to 2 main tasks: Analyzing and drawing.

Analyzing the image: Done in 3 steps. First, converting the images to grayscale, then applying the canny edge detection function, then returning straight lines using the hough function.

Drawing: The average_line() function uses the line segments returned by the hough line function to draw 2 main lines corresponding to the 2 lanes. I calculate the slope of each hough line to determine wheather in belongs to the right or left lane.
Then finding the A and B coefficients for the line equation y=Ax+B . Then I calculated the average coefficients for each line and used the average coefficients to draw the red extrapolated lines.
 

![example image](/examples/solidYellowCurve2.jpg)


### 2.Potential shortcomings with current pipeline

-The pipeline responsible for detecting lane lines works within a fixed portion of the image. If the car changes lanes, The lanes become less likely to be detected.

-The code might only work during the day. At nightime , edges are harder to detect.

-The code is useless in traffic jams or in cities because lane lines are barely visible. The same with snow and rain.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to eliminate the shakiness of the extrapolated lines drawn on the lanes. 

The pipeline works only for a specific image size, It can be modified to be flexible for a variety of image dimensions. 
