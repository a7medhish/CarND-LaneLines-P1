# **Finding Lane Lines on the Road** 



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

My pipeline consisted of 8 steps. First, I converted the images to grayscale, then I Used cany that is a cv2 method that  implemnts more like a derivitve of the image in order of detecting edges . after and then i use cv2.GaussianBlur for smothing the image .As I only interseted with the some part of the image i used a polygun by implementing a numpy fun. then I applied a mask for the rest of the picture so I can only detect edges withen the polygun . after that i used the hough_lines function that will draw the lines on the region of the interset with a certain thereshhold.However the desiered output was to implement only two lines so this is where the draw_lines fun cames. a funaction that i have used to draw the desired output lines by using the slope to split the lines by their slope and y intersept values .then I took the avarge of each set to fitt in two lines . after that I used the cv2.lines to draw those lines.last but not the least I used weighted_img for integrating both the orignal image and the lines image .   

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


the pipeline has some shortcomings when it comes to curves. If the lane turns at an angle great enough to move the lane "end" from the center of the graph, the detected lane lines will not align with reality. It's also possible the lane will move outside the "region_of_interest" we have defined.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be  By getting the error of the last frame for lane detaction so we can use it and do like machine learning regrassion model
Another potential improvement could be to
genarte a fun that will detect a desired thershhold and not by trial only 
