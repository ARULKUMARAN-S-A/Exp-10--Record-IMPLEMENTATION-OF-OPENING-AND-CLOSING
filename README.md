# Exp-10--Record-IMPLEMENTATION-OF-OPENING-AND-CLOSING

# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:
- Morphological Opening
- Morphological Closing

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
Create a blank image using NumPy.

### Step 3:
Insert text and small noise into the image using OpenCV.

### Step 4:
Display the original image.

### Step 5:
Create a structuring element (kernel) of suitable size.

### Step 6: Opening Operation
- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving larger objects.
- Display the opened image.

### Step 7: Closing Operation
- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 8:
Compare the original, opened, and closed images.

## Program

## Developed By

**Name: ARUL KUMARAN S A**

**Register No: 212224040030**

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read Image
img = cv2.imread("batman.jpg", 0)

# Display Original Image
plt.figure(figsize=(10,5))
plt.subplot(1,3,1)
plt.imshow(img, cmap='gray')
plt.title("Original Image")
plt.axis("off")

# Create Kernel
kernel = np.ones((5,5), np.uint8)

# Opening Operation
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

plt.subplot(1,3,2)
plt.imshow(opening, cmap='gray')
plt.title("Opening")
plt.axis("off")

# Closing Operation
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

plt.subplot(1,3,3)
plt.imshow(closing, cmap='gray')
plt.title("Closing")
plt.axis("off")

plt.show()
```



## Output

### Original Image
- The input image containing OPENCV text and noise is displayed.
- The image serves as the source for morphological processing.
<img width="453" height="294" alt="image" src="https://github.com/user-attachments/assets/ff815180-aee6-43fd-ad43-28570135603a" />


### Opening Operation
- Opening consists of Erosion followed by Dilation.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.
<img width="471" height="298" alt="image" src="https://github.com/user-attachments/assets/03baf4fd-dcdd-4b0f-9d3c-b5402232732a" />


### Closing Operation
- Closing consists of Dilation followed by Erosion.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.
<img width="447" height="297" alt="image" src="https://github.com/user-attachments/assets/f1a77cf2-7b76-4e90-8d54-0fe7f2826f6c" />


## Applications

### Opening
- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing
- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening
- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing
- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV.
