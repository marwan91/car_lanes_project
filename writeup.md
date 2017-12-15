**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline can be divided to 2 main tasks: Analyzing and drawing.

Analyzing the image: Done in 3 steps. First, converting the images to grayscale, then applying the canny edge detection function, then returning straight lines using the hough function.

Drawing: The draw_lines() function uses the line segments returned by the hough line function to draw 2 main lines corresponding to the 2 lanes. I calculate the slope of each hough line to determine wheather in belongs to the right or left lane.
Then finding the A and B coefficients for the line equation y=Ax+B . Then I calculated the average coefficients for each line and used the average coefficients to draw the extrapolated lines.


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![example image]car_lanes_project/examples/solidYellowCurve2.jpg)


### 2. Identify potential shortcomings with your current pipeline

-The code responsible for detecting lane lines works within a fixed portion of the image. If the car changes lanes, The lanes become less likely to be detected.

-The code might only work during the day. At nightime , edges are harder to detect.

-The code is useless in traffic jams or in cities because lane lines are barely visible. 


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to eliminate the shakiness of the extrapolated lines drawn on the lanes 

 
