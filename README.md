# Exp-7-Record-HOUGH-TRANSFORM
# Lane Detection

## Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective
Understand each stage of image processing

Learn how to build a complete computer vision pipeline

Practice writing code in guided sections

### Important Instruction:

👉 Write code ONLY in places marked as # Your Code Here 

👉 Do NOT modify any other part of the code

## Software Used

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm & Explanation

### : DIVYA PRIYA S
### Register No: 212225240037

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('Professional Portrait in Black Blazer (1).png')

```

```
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

```
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
```
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)
# Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
```
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
```
# Step 6: Using a for loop, draw the lines on the original image
# The lines variable contains the endpoints of the detected lines

for line in lines:
    x1, y1, x2, y2 = line  # Unpack the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines
```
```
# Display the image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```
```
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
```
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Expected Output

### Original image
<img width="654" height="413" alt="image" src="https://github.com/user-attachments/assets/e771d34f-012b-4d83-96ba-34d9d19f18d6" />

### Grayscale image
<img width="591" height="409" alt="image" src="https://github.com/user-attachments/assets/22b7883c-4f3d-454a-b88e-ca96104790c0" />

### Edge detected image
<img width="583" height="402" alt="image" src="https://github.com/user-attachments/assets/2214decb-bd9e-493a-a3bd-fae9793c3ea1" />

### Final edge detection output
<img width="590" height="405" alt="image" src="https://github.com/user-attachments/assets/01cad2f7-14b5-4b7c-9c4b-3d118125839e" />

## Instructions
Fill ONLY in # Your Code Here sections

Do NOT change existing code

Run step-by-step

Verify outputs

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

