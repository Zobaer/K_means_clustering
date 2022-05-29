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

**(a)** Two custom functions have been written, one for calculating distances between to pixel points in the image and other for calculating average of 'len' number of pixel points (for shifting the centroid). The functions are respectively:

- def cal_dist(x,y)
- def calc_avg(x,len)

**(b)** The image has been read by cv2.imread() function and it has been visualized whenever needed by cv2_imshow() function.

**(c)** The number of clusters K has been taken as input. We assumed the number of iterations to be 10 (it can be changed as needed, by visualizing the updated centroid values).

**(d) Next, K centroids are initialized randomly, but from the pool of pixel values available in the given image. the key function that helped us do this is random.choice(list).

**(e)** Inside loop, below two algorithmic steps of K-means clustering have been performed:

 - **Cluster assignment**: Each pixel from the image has been read, distances from all the centroids have been calculated using our custom calc_dist() function, the index of the minimum of them has been found out by numpy.argmin() function, and these indices are saved in a matrix called assigned_cluster. The indices saved in this matrix are from 0 to K-1 and denotes which cluster the pixel located at the same position (row & column) of the image is assigned to.
 - **Shift centroid**: We have the assigned clusters for each pixel. Now we have to group the pixels in the same cluster together and find the average. numpy.where(assigned_cluster == n) helped us find the indices of pixels which are assigned to cluster n. Then from the image, those pixels are taken and average has been calculated using the custom calc_avg() function. This will be the new centroid. (Note: we flattened out the assigned_cluster matrix and the image matrix for playing with indices more easily.)

**(f)** Above two steps are repeated and each time the updated centroids are printed in the output console to see if they are changing a lot or not. If they keep changing, then maximum number of iteration can be updated (increased) from the code.

**(g)** After the required number of interations are completed, the final centroid values have been printed and the image pixels are updated with there corresponding centroid values. the updated image has been visualized using cv2_image() function.

# Sample result
For K = 6:

![alt text](https://github.com/Zobaer/K_means_clustering/blob/main/input.png)

Enter the value of k (number of cluster): 6
[[190. 185. 194.]

[ 65. 139. 187.]

[ 20. 29. 26.]

[ 48. 38. 44.]

[ 95. 171. 253.]

[105. 212. 228.]]



[[135. 129. 134.]

[ 76. 76. 84.]

[ 32. 27. 18.]

[ 41. 32. 34.]

[103. 96. 98.]

[103. 116. 110.]]

_______________________________________


[[103. 116. 110.]

[ 41. 47. 60.]

[ 18. 18. 16.]

[ 32. 34. 33.]

[ 89. 83. 92.]

[ 68. 68. 66.]]

_______________________________________


[[103. 116. 110.]

[ 32. 36. 33.]

[ 18. 18. 16.]

[ 34. 33. 32.]

[ 60. 51. 59.]

[ 41. 47. 60.]]

__________________________________________

[[103. 116. 110.]

[ 34. 33. 29.]

[ 18. 18. 16.]

[ 32. 27. 21.]

[ 47. 60. 60.]

[ 41. 32. 36.]]

__________________________________________


[[103. 116. 110.]

[ 32. 27. 29.]

[ 18. 18. 16.]

[ 21. 22. 23.]

[ 41. 32. 36.]

[ 34. 33. 32.]]

___________________________________________

[[103. 116. 110.]

[ 27. 24. 25.]

[ 16. 14. 15.]

[ 18. 18. 21.]

[ 41. 32. 34.]

[ 33. 32. 29.]]

______________________________________________

[[103. 116. 110.]

[ 21. 22. 24.]

[ 14. 15. 13.]

[ 18. 18. 16.]

[ 41. 32. 34.]

[ 32. 27. 29.]]

______________________________________________


[[103. 116. 110.]

[ 18. 18. 21.]

[ 13. 14. 15.]

[ 16. 14. 15.]

[ 41. 32. 34.]

[ 32. 27. 28.]]

_______________________________________________

[[103. 116. 110.]

[ 18. 18. 16.]

[ 14. 13. 14.]

[ 15. 15. 15.]

[ 41. 32. 34.]

[ 32. 27. 28.]]

______________________________________________


[[103. 116. 110.]

[ 18. 18. 16.]

[ 12. 14. 11.]

[ 15. 13. 14.]

[ 41. 32. 34.]

[ 32. 27. 28.]]

(These are cluster centers for K=6)



