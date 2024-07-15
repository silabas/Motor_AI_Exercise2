# Motor AI Exercise2

This exercise includes writing a Python script that combines 3 vector data (road bounds, road markings, buildings) into a single raster RGB mask with following pixel values:

- road bound: [0, 0, 200]
- buildings: [255, 0, 0]
- broken line: [0, 20, 10]
- cycle lane: [0, 40, 0]
- dashed line: [0, 45, 70]
- pedestrian crossing: [0, 100, 0]
- solid line: [0, 45, 0]
- stop line: [0, 85, 0]

Mask image result:
![image](https://github.com/user-attachments/assets/a8494e63-c74a-41cb-9d7e-16362e07e712)


b) Raster masks with similar pixel values were loaded into an ML pipeline but the process broke down before the
training could commence. Which feature(s) were likely to be the culprit(s)? 

In the case of this exercise, the script generating new pixel values like (0,20,210) in the output image mask. Because it is summing up pixel values where road markings and road bound features are intersected. If the model is specified to train certain number of class, then in the end we will feed the model with more classes than the expected so this situation might break down ML the pipeline before training process commence. 

So the road markings and road bounds features are the reasons of this issue.

We can solve this situation with giving priority to the road marking classs. The output mask image would have pixel values of road markings for the areas where road bounds and road markings are intersected. And for the areas where there is only road bounds, the pixel values would be (0,0,200).
