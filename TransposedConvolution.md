# Upsampling and Transposed Convolution
Convolution generally reduces the dimension of the image. Nut in several task sych as Imahe reconstruction, Image Segmentation or autoencoders, you need to preserve the output dimiension. This can be done in two ways:

1. Perform Half-Padding to preserve dimension at every step of convolution
2. Perform Transpose Convolution to recover dimension of the image from a lower dimension.

We have already discussed Half-Padding in the previous section, Here we will discuss Transpose Convolution.

## Nearest Neighbors
In Nearest Neighbors, as the name suggests we take an input pixel value and copy it to the K-Nearest Neighbors where K depends on the expected output.
<img width="500" alt="Screen Shot 2023-01-08 at 1 27 45 AM" src="https://user-images.githubusercontent.com/46320499/211168317-66ed5f0d-6f56-4768-be76-46bbb80894cc.png">

## Bi-Linear Interpolation
<img width="500" alt="Screen Shot 2023-01-08 at 1 28 35 AM" src="https://user-images.githubusercontent.com/46320499/211168438-a334e587-5c20-43be-984e-d427294dc981.png"><br>
Converting 2*2 into 4*4, the spaces in the middle are file by linear interpolatrion of the values in the 2*2 matrix.

## Bed of Nails



