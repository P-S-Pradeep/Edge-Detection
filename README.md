# Edge-Detection
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary modules.

### Step2:
For performing edge detection on a image.

* Sobel
```
sobelx=cv2.Sobel(img,cv2.CV_64F,1,0,5)
sobely=cv2.Sobel(img,cv2.CV_64F,0,1,5)
sobelxy=cv2.Sobel(img,cv2.CV_64F,1,1,5)
```

* Laplacian
```
Laplacian=cv2.Laplacian(img,cv2.CV_64F)
```

* Canny
```
canny=cv2.Canny(img,120,150)
```

### Step3:
Display all the images with their respective edge detected images.
 
## Program:

``` Python
# Import the packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise
image1=cv2.imread ('rubix.png') 
gray = cv2.cvtColor(image1,cv2.COLOR_BGR2GRAY)
plt.title('GRAY IMAGE')
plt.imshow(gray,cmap = 'gray')

# SOBEL EDGE DETECTOR
img = cv2.GaussianBlur(gray,(3,3),0)
sobelx = cv2.Sobel(gray,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(gray,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(gray,cv2.CV_64F,1,1,ksize=5)
plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(gray,cmap = 'gray')
plt.title('Original')
plt.axis("off")

plt.subplot(2,2,2)
plt.imshow(sobelx,cmap='gray')
plt.title('sobelx')
plt.axis("off")

plt.subplot(2,2,3)
plt.imshow(sobely,cmap='gray')
plt.title('sobely')
plt.axis("off")

plt.subplot(2,2,4)
plt.imshow(sobelxy,cmap='gray')
plt.title('sobelxy')
plt.axis("off")
plt.show()

# LAPLACIAN EDGE DETECTOR
laplacian = cv2.Laplacian(gray,cv2.CV_64F)
plt.imshow(laplacian,cmap='gray')
plt.title('laplacian')
plt.axis("off")
plt.show()

# CANNY EDGE DETECTOR
canny_edges = cv2.Canny(gray, 120, 150)
plt.imshow(canny_edges,cmap='gray')
plt.title('canny_edges')
plt.axis("off")
plt.show()

```
## Output:
### SOBEL EDGE DETECTOR
![image](https://user-images.githubusercontent.com/102652887/169021358-b607d565-415a-44e7-8712-f301a29f2629.png)

### LAPLACIAN EDGE DETECTOR
![image](https://user-images.githubusercontent.com/102652887/169021412-d684359a-129d-4dff-a503-1d3cdf3b8575.png)


### CANNY EDGE DETECTOR
![image](https://user-images.githubusercontent.com/102652887/169021453-f5ed4b10-8b35-4774-9a1c-dbe0ad337c88.png)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
