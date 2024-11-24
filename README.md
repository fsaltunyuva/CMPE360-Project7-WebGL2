# CMPE360 Computer Graphics

## Project 7 - WebGL 2

You will practice modelling and viewing transformations with boxes.html and boxes.js 
then answer some questions.

Goals of this project are:
- <ins>Viewing Transformations</ins>: through *lookAt* or equivalent modelling transformations
- <ins>Projection Transformations</ins>: through perspective, ortho
- <ins>Modelling Transformations</ins>: rotate*, translate, scale and matrix stack.

### Part 1
Start with boxes.html and boxes.js form Part1 folder. When you run boxes.html, you 
should see as below firstly. 

![Figure 1](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%201.png)

This program draws a basic coordinate system with a green x-axis, a red y-  axis, and a blue z-axis. These will be referred to in the instructions as the axes.
With the initial camera settings, you are looking directly down the z-axis so you will not see it.

Make the following changes.

1. Comment out the lookAt() call and replace it with translate() with parameters 
(0,0,-15). Is there any change in the display? Why ? Why not? Please explain in 
detailed and add image.

2. Comment out both the lookAt() and translate() lines. What happens? Why?

4. Take a look at the perspective() call. The aspect ratio you were originally given 
was 1.0.
    a. What happens when the aspect ratio is 1.0 and you change the canvas 
dimensions in boxes.html to width=”600”, height=”600? 
    b. How about width=”1024” and height=”1024”
    c. The aspect ratio allows us to compensate for different shapes of canvas. 
Study there commendations in point 2. of WebGLAnti-Patterns, then 
modify the aspect ratio in your perspective call so that it is an appropriate 
ratio of width to height based on the actual dimensions of the viewing 
area. Test the result with the two suggested canvas shapes to be sure you 
got it right.

5. Draw a wireCube centered (0,0,0) relative to the axes. You can use the provided 
buffers and related shape data. Do this in the render function.

6. Move this cube so that it is centered as (1,0,0) relative to the axes.

7. Draw a second cube after the first –in a new color(blue) if you can- and rotate 
it 45 degrees around the y-axis. 
8. Place this rotated cube directly above the first cube. It will be centered at (1,0,0) 
relative to the axes. Be careful of the order of transformation. 

9. The perspective view makes the two cubes look a little awkward. Try using 
orthographic projection instead of the perspective call. The function for that is: 
ortho. Use left, right, bottom, top, near and far values that include the whole 
scene and not much more. See the picture for expected results.

![Figure 2](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%202.png)

10. Rotate everything (using modelling transformations NOT lookAt) so that 
looking down at the top of the boxes and seeing the blue z-axis (and no red y- 
axis). See the picture for expected results. 

![Figure 3](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%203.png)

11. Rotate everything so that you can see all three axes along with the cubes. See 
the picture for expected results.

![Figure 4](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%204.png)

12. Camera Position Adjustment: The camera can be moved up, left, down, or right 
using the 'w', 'a', 's', and 'd' keys.

### Part 2
When you open Part2 folder and run robot_arm.html you should see like below default robot arm. 

![Figure 5](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%205.png)

- First load the application and see how it works. Try pressing lower and uppercase 'e' to 
move the elbow. Try pressing lower and uppercase 's' to move the shoulder.

- Now, add three fingers and a thumb to the robot. Use matStack.push() and 
matStack.pop() to separate the transformations for each digit. Do not attempt to "untransform" 
with an inverse rotate, translate or scale.

- Finally, add some code that will make the finger and thumb move apart when 'f' is 
pressed and together when 'F' is pressed. The center of rotation should be at the wrist.

![Figure 6](https://github.com/fsaltunyuva/CMPE360-Project7-WebGL2/blob/main/Figures/Figure%206.png)
