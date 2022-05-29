# K_means_clustering
An image has been read using python code and K-means clustering has been performed on it. K is taken as an input. The input image is below:

![alt text](https://github.com/Zobaer/K_means_clustering/blob/main/input.png)

# Dependencies

Dependencies are:

import numpy as np

import cv2

from google.colab.patches import cv2_imshow

import random as rnd

#Although below two are imported in code, they are never really used:

import matplotlib.pyplot as plt

import math

# Complete explanation

A python code in colab has been written to perform the required K-means clustering. the code is available in colab notebook K_means_clustering.ipynb

a) Two custom functions have been written, one for calculating distances between to pixel points in the image and other for calculating average of 'len' number of pixel points (for shifting the centroid). The functions are respectively:

def cal_dist(x,y)

def calc_avg(x,len)
