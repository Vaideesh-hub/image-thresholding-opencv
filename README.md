# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

## Developed By

**Name:** Vaideeshwaran G

**Register No:**  212225240178

## Program
```
# Step 1: Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Step 2: Load the input image using OpenCV
image = cv2.imread('lenna.jpeg')

if image is None:
    raise FileNotFoundError("image.jpg was not found. Place image.jpg in the same folder as this notebook.")
```
```
# Step 3: Convert the input image to grayscale
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(6,5))
plt.imshow(gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

## Output

<img width="602" height="550" alt="Screenshot 2026-11-22 110802" src="https://github.com/user-attachments/assets/94ff0d26-0cc9-449a-9e64-b260a58f262b" />

## Program
```
# Step 4: Global Thresholding
threshold_value = 127
_, global_threshold = cv2.threshold(
    gray,
    threshold_value,
    255,
    cv2.THRESH_BINARY
)

plt.figure(figsize=(6,5))
plt.imshow(global_threshold, cmap='gray')
plt.title('Global Thresholding')
plt.axis('off')
plt.show()
```

## Output

<img width="596" height="570" alt="Screenshot 2026-11-22 115114" src="https://github.com/user-attachments/assets/47969b8e-1c67-4e2a-9b67-ec53dd9fd8b7" />

## Program
```
# Step 5: Adaptive Mean Thresholding
adaptive_mean = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

# Adaptive Gaussian Thresholding
adaptive_gaussian = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)

plt.figure(figsize=(12,5))

plt.subplot(1,2,1)
plt.imshow(adaptive_mean, cmap='gray')
plt.title('Adaptive Mean Thresholding')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output

<img width="820" height="377" alt="Screenshot 2026-11-22 115207" src="https://github.com/user-attachments/assets/1e6f4a82-9664-4bdf-988f-0c1ac9bb12dc" />

## Program
```
# Step 6: Otsu's Thresholding
otsu_threshold_value, otsu_threshold = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

print("Otsu's Optimal Threshold Value:", otsu_threshold_value)

plt.figure(figsize=(6,5))
plt.imshow(otsu_threshold, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')
plt.show()
```

## Output

<img width="536" height="602" alt="Screenshot 2026-11-22 115236" src="https://github.com/user-attachments/assets/ec012798-1f15-496e-beb2-c2e105adab19" />

## Program
```
# Step 7: Compare all thresholding methods
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(2,3,2)
plt.imshow(gray, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(2,3,3)
plt.imshow(global_threshold, cmap='gray')
plt.title('Global Thresholding')
plt.axis('off')

plt.subplot(2,3,4)
plt.imshow(adaptive_mean, cmap='gray')
plt.title('Adaptive Mean Thresholding')
plt.axis('off')

plt.subplot(2,3,5)
plt.imshow(adaptive_gaussian, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.axis('off')

plt.subplot(2,3,6)
plt.imshow(otsu_threshold, cmap='gray')
plt.title("Otsu's Thresholding")
plt.axis('off')

plt.tight_layout()
plt.show()
```

## Output

<img width="776" height="507" alt="Screenshot 2026-11-22 115333" src="https://github.com/user-attachments/assets/bb7b47ef-f695-495e-863c-b845ff55ae34" />

## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
