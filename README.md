# EX:1 COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.


## Program:
#### Developed By: Thiyagarajan A
#### Register Number: 212222240110

### i)Read and Display an Image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Load an image from your local directory
image_path = 'dog.jpg'  # Replace with your image path
image = cv2.imread(image_path)
# Step 1: Display the Original Image
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()

```
![image](https://github.com/user-attachments/assets/39578b12-bb89-4d39-b65d-c469b33c4209)

### ii)Draw Shapes and Add Text

```

# Step 2: Draw Shapes and Add Text
image_with_line = image.copy()
cv2.line(image_with_line, (0, 0), (image.shape[1], image.shape[0]), (255, 0, 0), 2)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_with_line, cv2.COLOR_BGR2RGB))
plt.title('Image with Line')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/4f77b50b-c1c3-475a-9b4d-2fa64351584d)

```

image_with_circle = image.copy()
cv2.circle(image_with_circle, (image.shape[1] // 2, image.shape[0] // 2), 100, (0, 255, 0), 2)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_with_circle, cv2.COLOR_BGR2RGB))
plt.title('Image with Circle')
plt.axis('off')
plt.show()

```
![image](https://github.com/user-attachments/assets/cc49f0df-430c-41ee-aab0-dc8c521d1027)
```
image_with_rectangle = image.copy()
cv2.rectangle(image_with_rectangle, (100, 50), (250, 250), (0, 0, 255), 2)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_with_rectangle, cv2.COLOR_BGR2RGB))
plt.title('Image with Rectangle')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/1a1edabe-b47c-4abb-be31-2d9e92d98a2c)
```
image_with_text = image.copy()
cv2.putText(image_with_text, 'OpenCV', (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_with_text, cv2.COLOR_BGR2RGB))
plt.title('Image with Text')
plt.axis('off')
plt.show()

```

![image](https://github.com/user-attachments/assets/6c1dffe7-b38d-4bc5-ad88-e8c78a616dcb)

### iii)Image Color Conversion
```
# Step 3: Image Color Conversion
image_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_hsv, cv2.COLOR_BGR2RGB))
plt.title('Image in HSV')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/6f9b9bb3-7859-4ca9-8323-c5487b8019d5)
```
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.figure(figsize=(6, 4))
plt.imshow(image_gray, cmap='gray')
plt.title('Image in GRAY')
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/ee4834df-2f4f-4af6-8ddb-94041e35cf58)
```

image_ycrcb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image_ycrcb, cv2.COLOR_BGR2RGB))
plt.title('Image in YCrCb')
plt.axis('off')
plt.show()

```
![image](https://github.com/user-attachments/assets/2a34e3d5-fc4d-41dd-9859-dee2b096a51a)


### iv)Access and Manipulate Image Pixels
```
# Step 4: Access and Manipulate Image Pixels
pixel_value = image[100, 100]
print(f'Pixel value at (100, 100): {pixel_value}')
image[200, 200] = [255, 255, 255]
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Image with Manipulated Pixels')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/c1518625-b8f1-423b-99a0-2e06d1c61b4b)

### v)Image Resizing
```
# Step 5: Image Resizing
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB))
plt.title('Resized Image')
plt.axis('off')
plt.show()
```


![image](https://github.com/user-attachments/assets/7637f4e7-edd6-4b50-ac46-434018ff1c38)


### vi)Image Cropping
```
# Step 6: Image Cropping
cropped_image = image[50:150, 50:150]
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title('Cropped Image')
plt.axis('off')
plt.show()

```
![image](https://github.com/user-attachments/assets/573180ad-f8d3-4997-9f2b-2112e47c7de1)


### vii)Image Flipping

```
# Step 7: Image Flipping
flipped_image_horizontal = cv2.flip(image, 1)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(flipped_image_horizontal, cv2.COLOR_BGR2RGB))
plt.title('Flipped Horizontally')
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/5b09a56c-4e7e-4286-ad8c-efa003c13240)
```
flipped_image_vertical = cv2.flip(image, 0)
plt.figure(figsize=(6, 4))
plt.imshow(cv2.cvtColor(flipped_image_vertical, cv2.COLOR_BGR2RGB))
plt.title('Flipped Vertically')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/d3440ed1-c897-42e3-83a8-be32daa7afcf)



### viii)Write and Save the Modified Image
```
# Step 8: Write and Save the Modified Images
cv2.imwrite('image_with_line.jpg', image_with_line)
cv2.imwrite('image_with_circle.jpg', image_with_circle)
cv2.imwrite('image_with_rectangle.jpg', image_with_rectangle)
cv2.imwrite('image_with_text.jpg', image_with_text)
cv2.imwrite('resized_image.jpg', resized_image)
cv2.imwrite('cropped_image.jpg', cropped_image)
cv2.imwrite('flipped_horizontal.jpg', flipped_image_horizontal)
cv2.imwrite('flipped_vertical.jpg', flipped_image_vertical)
```

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







