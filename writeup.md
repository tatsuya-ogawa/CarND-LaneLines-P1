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

My pipeline consisted of 5 steps. 
1. Converted the images to grayscale
2. Apply gaussian blur to smooth image
3. Apply Canny edge detection,so get edges
4. Mask edges to filter available area
5. Get HoughLine from edges above

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...
1. Filter available line to apply threshold of slopes,and divide lines to left side and right side
2. Divide lines into points to apply linear regression
3. Get slope and intercept with applying scipy linregress


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are lack of lines in images, It can not detect the line candidate parts.

Another shortcoming could be weak to noise, so many noise leads to wrong slope.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apply time series supplement.
It would be supplementing loss of lines and leveling of incorrect slopes.

