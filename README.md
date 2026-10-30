
# EXP. 01 – IMAGE HANDLING AND PIXEL TRANSFORMATION USING OpenCV

## NAME: Tharshini.M
## REG.NO: 212224230287

## AIM
Write a Python program using OpenCV that performs the following tasks:

1. Read and display an image.
2. Adjust the brightness of an image.
3. Modify the image contrast.
4. Generate a third image using bitwise operations.

## Software Required
- Anaconda - Python 3.7
- Jupyter Notebook

## Algorithm

# Step 1:
Load an image from your local directory and display it.

# Step 2:
Create a matrix of ones with data type `float64` to adjust brightness.

# Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display all three images.

# Step 4:
Modify image contrast using scaling factors of 1.1 and 1.2. Display the original and contrast-adjusted images.

# Step 5:
Split the image (`Image.png`) into B, G, R components and display the channels.

---

## 1. Import the Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## 2. Read and Display the Original Image

```python
img = cv2.imread('Image.png', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```


## OUTPUT:
<img width="219" height="310" alt="{4E63B6B8-B60D-4610-9145-C3AD12609C86}" src="https://github.com/user-attachments/assets/68cd8bf8-6766-4925-bbd1-9a95bda0fad2" />



## 3. Print Image Width, Height and Channels

```python
height, width, channels = img.shape

print("Image Width:", width)
print("Image Height:", height)
print("Image Channels:", channels)
print("Image Shape:", img.shape)
```

## 4. Draw a Line from Top-Left to Bottom-Right

```python
line_img = cv2.line(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 9)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="216" height="308" alt="{869DB184-33AC-4D3B-AAFA-B3DBDE1E194A}" src="https://github.com/user-attachments/assets/9c70aaf0-81c0-4981-a85d-e0c688385956" />




## 5. Draw a Circle on the Image

```python
circle_img = cv2.circle(img_rgb.copy(), (400, 300), 150, (255, 165, 0), 10)

plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="224" height="307" alt="{5B411C9E-E3B4-454D-9F01-8F4900711192}" src="https://github.com/user-attachments/assets/00055b26-6791-411c-8890-ed23e7cfd202" />



## 6. Draw a Rectangle Around the Image

```python
rectangle_img = cv2.rectangle(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 10)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="214" height="300" alt="{7118BBE2-3882-4D5D-8B23-5D41AA110437}" src="https://github.com/user-attachments/assets/594f1f52-e026-423e-8ee3-b712e7ecfdc1" />



## 7. Add Text to the Image

```python
text_img = cv2.putText(
    img_rgb.copy(), "Nikila", (100, 100),
    cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 165, 0), 10
)

plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="214" height="298" alt="{73F09124-57DD-4F4F-9211-D8523FDDFE92}" src="https://github.com/user-attachments/assets/19a7da7f-8604-4ff4-b637-f100ec48bdfc" />



## 8. Save the Image as a PNG File

```python
cv2.imwrite('Output.png', img)
```

## 9. Read the Saved Image and Convert it to Grayscale

```python
image = cv2.imread('Output.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="211" height="304" alt="{00B51F64-D85A-4C97-B438-27148E40EDBB}" src="https://github.com/user-attachments/assets/74304cb7-2c1a-434b-91db-60e2da51b82c" />




## 10. Display the Original RGB Image

```python
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="207" height="297" alt="{8B1CFE4A-5D79-43AF-9925-A5D6D56A4B40}" src="https://github.com/user-attachments/assets/10ed9b63-20ca-4b5c-94f7-d79e35afa1d4" />




## 11. Convert RGB Image to HSV

```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="212" height="300" alt="{2E719585-953A-4AAD-90F1-D9FEC10D70C4}" src="https://github.com/user-attachments/assets/0ac85258-cc74-4536-a0c9-e368e3609226" />



## 12. Convert RGB Image to YCrCb

```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="210" height="302" alt="{94F28709-63FD-40D4-AF64-9D16D0CFB2C2}" src="https://github.com/user-attachments/assets/8ce475de-906f-4570-ae11-e43c6646e0f4" />



## 13. Convert HSV Back to RGB

```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="210" height="302" alt="image" src="https://github.com/user-attachments/assets/b0b89f5e-442a-4a4e-8e53-5dfa1a1f11a7" />



## 14. Modify a Block of Pixels to White

```python
image = cv2.imread('Image.png')
image[200:500, 200:500] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="212" height="307" alt="{3DF83898-C431-4616-9BA9-0853B9393882}" src="https://github.com/user-attachments/assets/cf195e76-027d-4fca-ab70-896bf3ace4f9" />



## 15. Resize the Image to Half its Size

```python
image = cv2.imread('Image.png')
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

print("Resized Image Shape:", resized_image_rgb.shape)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="359" height="302" alt="{66F8B0D6-0DB5-42E5-A81F-157E09D87E0D}" src="https://github.com/user-attachments/assets/db5be063-77f8-4d2c-8246-bc3bc9f01402" />



## 16. Crop a Specific Region of the Image

```python
image = cv2.imread('Image.png')
roi = image[50:350, 50:350]

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="279" height="303" alt="{CAE3A1FF-503B-44FE-875B-35887E7C16E4}" src="https://github.com/user-attachments/assets/571730c6-b479-467b-b384-18f056d435d2" />




## 17. Flip the Image Horizontally

```python
image = cv2.imread('Image.png')
flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="210" height="300" alt="{5D18EBAB-1B1C-449B-A6AB-1B58BBA748CC}" src="https://github.com/user-attachments/assets/a2f2bfb9-ddc1-4c40-ab01-86f4a0147ec6" />



## 18. Flip the Image Vertically

```python
flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="214" height="306" alt="{54E6F8C0-4FA1-4DF8-AE18-9FF6BF9BB839}" src="https://github.com/user-attachments/assets/547ec21f-8cee-4447-a2d5-88bdf80986be" />



## Result

Thus, the images were read and displayed, brightness and contrast adjustments were made, colour channels were split and merged, and bitwise operations were performed successfully using Python and OpenCV.
