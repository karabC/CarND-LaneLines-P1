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

My pipeline consisted of following steps:
1. Turn the image to the gray scale
2. Apply Candy Edge Detection with Gaussian blur before
3. Masked out the non-interested region (with parameter defined)
4. Finding set of lines through hough transformation
5. Filter unneccesary lines and split lines into two sets, i.e. Left and Right
6. draw two extrapolate lines which calculated from the average position in each groups of lines.




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the line in the interested region is too sparse. No line could be formed by the hough transform. Although this could be tuned by modifying the hough parameter, it would increase the noise especially in the challange case.

### 3. Suggest possible improvements to your pipeline

One possible improvement is to adding several sets of parameter as suplement logic. If no lines are finally formed either in left or right-side, another set of parameter, with less tighter parameter for hough transformation, could be applied to retreive new results.

Still, there are several parameters for these computer vision algorithm and I have no idea how to generalize these parameters in a more dynamic approach. 


Another possible improvement i could think of is to provide short term memory to the algorithm. By simply using last five frames's result instead of one could stablize the output. 