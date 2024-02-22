# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By:T MOUNISH
### Register Number:212223240098 


## Output:
### i) Read and display the image
```Python
import cv2
color_image = cv2.imread('cat.jpg',1)
cv2.imshow('colorimage',color_image)
cv2.waitKey(0)
```
  </td>
  <td>

#### OUTPUT:
![cat1](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/01e8f266-7223-45ad-8a5c-b06bf55b9861)

</td>
</tr>



<tr>
  <td width=50%>
    
### ii)Write the image
```Python
import cv2
image=cv2.imread('cat.jpg',0)
cv2.imwrite('new1.jpg',image)
```
  </td>
  <td>

#### OUTPUT:

![cat-1 2](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/6d41a7a8-85a0-4151-8911-957ec4d071dc)

</td>
</tr> 
<tr> 
  <td width=50%>

### iii)Shape of the Image
```Python
import cv2
image=cv2.imread('cat.jpg',1)
print(image.shape)
```
  </td> 
  <td>

#### OUTPUT:
![cat1 3](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/287bbd19-d0b5-4874-91ca-312a86d195b0)

  </td>
  </tr> 
  <tr>
    <td>

### iv)Access rows and columns
```Python
     import random
     import cv2
     image=cv2.imread('cat.jpg',1)
     image=cv2.resize(image,(400,400))
     for i in range (150,200):
       for j in range(image.shape[1]):
            image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
     cv2.imshow('part image',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

#### OUTPUT:
![cat1 4](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/cbd08533-8793-4fc1-b5e1-1be264de273e)


 </td>
 </tr>
 <tr>
  <td width=50%>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('cat.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
  </td>
  <td>

#### OUTPUT:
![cat1 5](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/97062aaf-ae92-46fc-9550-4d11dc49be64)


 </td>
 </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('cat.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![cat1 6](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/b76adc0a-3204-4e70-b53b-8746a521b05d)



### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('cat.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
#### OUTPUT:
![cat1 7](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/4d725bf5-2079-4f54-993c-4036917b3447)



### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('cat.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
#### OUTPUT:
![cat1 8](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/7cd6d080-859b-49c9-8efe-e955464161f8)



### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('cat.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![cat1 9](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/243ea2ed-af99-4ba2-8d01-d171b6f56041)



### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("cat.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
#### OUTPUT:
![cat1 10](https://github.com/Kesavasai20/COLOR_CONVERSIONS_OF-IMAGE/assets/138849303/546dba9b-2918-42b4-87cd-07de4cf8e449)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







