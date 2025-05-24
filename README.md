# Canny-Edge-detection

## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Output:
```python
import cv2
import numpy as np

# Load the image
image = cv2.imread('boy.jpg')  # Replace with your image path
if image is None:
    raise ValueError("Image not found. Check the file path.")

# Convert to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

![image](https://github.com/user-attachments/assets/bf1f76c4-8d52-42a6-8d6e-900a68e2fb74)

### SOBEL EDGE DETECTOR
```py
# Detect edges in X and Y directions
sobelx = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)
sobely = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)
sobel_combined = cv2.magnitude(sobelx, sobely)
sobel_combined = cv2.convertScaleAbs(sobel_combined)
```
![image](https://github.com/user-attachments/assets/3a4ffdc3-807b-4fd9-b10f-e3a95fa1c9bb)

![image](https://github.com/user-attachments/assets/b942ffcf-1f93-4528-878e-09d5063442a2)

![image](https://github.com/user-attachments/assets/73969079-1eb2-40aa-b6ca-b01254533eeb)



### LAPLACIAN EDGE DETECTOR
```py
laplacian = cv2.Laplacian(gray, cv2.CV_64F)
laplacian = cv2.convertScaleAbs(laplacian)
```
![image](https://github.com/user-attachments/assets/cbf94aac-c035-4696-8d76-073822aa0a83)




### CANNY EDGE DETECTOR
```py
canny = cv2.Canny(gray, 100, 200)  # Adjust thresholds as needed

```
```py
cv2.imshow('Original', image)
cv2.imshow('Sobel X', cv2.convertScaleAbs(sobelx))
cv2.imshow('Sobel Y', cv2.convertScaleAbs(sobely))
cv2.imshow('Sobel Combined', sobel_combined)
cv2.imshow('Laplacian', laplacian)
cv2.imshow('Canny', canny)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/9ba90325-7d81-4e14-a391-28d3412cadc9)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
