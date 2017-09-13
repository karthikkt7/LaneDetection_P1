# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

Solution:
1.Detect the lanes using the Canny edge filter and Hough transformation by the thresholds respective to the functions
2.Lines are classified into right and left lane based on the slope. Slope which is negative is classified as left lane, Slope which is positive is classifed as right lane.
3.Eliminate the points lying out by setting the threshold for the slope
4.Calculate the average slope of all the line segments for the right and left lanes respectively
5.Find the point for extrapolation from the average position of all line segments
6.Detect the lanes!!
![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline and suggestions
1.The problem in the "challenge" video is that in the road, at some point of time, the color of the road gets gray and here there
is a detection by Canny edge and hough transformation. By looking at the brightness or possibly contrast, one could eliminate this
2.Finding the extrapolation point can be achieved by Storing the previous frame position, because we are using two adjacent frames which do not change drastically in the information
3.Shifting the lanes with different color can be a failure or needs bit more improvisation into it.
4.If there are lane overlaps (during construction on roads, new lanes are overlapped or drawn side by the existing lanes, then this requires again separation somehow between them since the chosen region of interest covers both the lanes)





