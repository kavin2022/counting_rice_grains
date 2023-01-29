
# Problem Statement
1. To identify rice in the given image (overlapping rice also included) and count the total , broken and full rice

# Approach
1. used watershed algorithm to detect rice from the image and to get the area .
2. using area ,build a ml algorithm to differentiate broken and full grain

![](../../Downloads/Blank diagram.png)

# Repository detail
This repository contains a Python script that utilizes the contour and watershed algorithms to count the number of grains of rice in an image. The script is implemented using the OpenCV library.


The repository contains the following files:

1. rice_counting.py: this script that performs the rice grain detection from the image
2. data: images with rice as data
3. requirements.txt: a list of dependencies needed to run the script
4. area.json : it contains the output of the rice_counting.py
   1. it includes - total count
   2. area of each rice grain
   3. some statistics like avg area of rice per image ,median area of rice per image
5. counting_and_finding_area : 
   1. it utilizes the rice_counting.py to detect rice grains and export the results to area.json
   2. it contains code to export data which is needed to train the machine learning model which will categorize broken and full grain
   3. data file exported by this code are stored in area_data , data/train_solved ,data/test_solved
   4. area_data : contains area of the rice per image
   5. data/train_solved : contains image with count label(output of watershed algorithm)
   6. data/test_solved : contains image with count label(output of watershed algorithm)
6. model_building_to_categorize_rice : contains code to build model which categorizes the rice and the best model is exported as finalized_model.pkl
7. prediction : using the finalized_model.pkl we predict the category of rice (broken or full) given the area
   1. output - count of broken, full , total rices
      1. data is stored in result 

# Result

## sample input of the image:
![](data/train/mixed_grain_1.jpg)
## sample output of the image:
![](data/train_solved/solved_watershed_mixed_grain_1.jpg)

# Count of rice:

1. total : 806
2. broken : 101
3. full : 302