## Ex.No:03
## Histogram-of-an-images
## Name:G.Ramanujam
## Reg.No:212224240129

## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
img=cv2.imread('Parrot.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img,cmap='gray')
plt.title('Original Image')
plt.show()
```
```
# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
# Equalize histogram
img_eq = cv2.equalizeHist(img)
 #Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```
# Display the images.
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
# Read the color image.
img = cv2.imread('Parrot.jpg', cv2.IMREAD_COLOR)
# Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
#Perform histogram equalization only on the V channel, for value intensity.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
# Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized')
plt.show()
```
```
# Display the images.
#plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```
# Display the histograms.
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output:

<img width="712" height="490" alt="Screenshot 2025-09-05 223045" src="https://github.com/user-attachments/assets/e6a15480-c36d-4008-b51c-9bd1d1efe7a3" />

<img width="772" height="549" alt="Screenshot 2025-09-05 223056" src="https://github.com/user-attachments/assets/253645da-091e-4ba6-b484-de13b6fe1869" />

<img width="817" height="602" alt="Screenshot 2025-09-05 223106" src="https://github.com/user-attachments/assets/fc1b297b-738e-4621-912b-69f4a6935e06" />

<img width="739" height="519" alt="Screenshot 2025-09-05 223115" src="https://github.com/user-attachments/assets/cd56aeda-6e1b-412a-b50e-041eb408a078" />

<img width="756" height="522" alt="Screenshot 2025-09-05 223125" src="https://github.com/user-attachments/assets/0442ba33-11f9-4803-aedb-ff36d48a8231" />

<img width="777" height="545" alt="Screenshot 2025-09-05 223134" src="https://github.com/user-attachments/assets/f4305ab5-cbc0-44e6-a800-4748d8aa4ad3" />

<img width="826" height="544" alt="Screenshot 2025-09-05 223144" src="https://github.com/user-attachments/assets/e6b24274-3491-4ad3-9870-46515d135747" />


<img width="900" height="334" alt="Screenshot 2025-09-05 223200" src="https://github.com/user-attachments/assets/fdb6eaef-7b91-4f23-8135-f1cd38456166" />


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
