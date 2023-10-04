# Lab 2: The Number Plate Challenge: Convolution, Filter and Enhancement

> We run our labs with [Python 3.6+](https://www.python.org/downloads/).
> For Windows, you might want to use [Conda](https://www.anaconda.com/products/distribution). 

## Using the lab sheet

There are two ways to use the lab sheet, you can either:

- [create a new repo from this template](https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/generate) - **this is the recommended way**
- download a [zip file](https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/archive/master.zip)

## Task 1: Convolution Basics 

1. Your first task is to write a small program that performs convolution between an input image (e.g. the mandrill image) and a kernel image (e.g. the simple 3x3 image given below). 
2. Implement the convolution function yourself by accessing pixels – for the moment ignore the OpenCV commands that can perform convolution. The operation is so fundamental to image processing that you should write it yourself at least once. 
3. Test your program on the mandrill image and the kernel below. What can you say about the output produced? Why do we need the factor 1/9?
4. Play around with the kernel values and see what effect it has on the image. Try a set of values that will sharpen the image.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/conv3x3.png" height=150> 

<details>
    <summary>Hint1</summary>
<img src="https://miro.medium.com/max/790/1*1okwhewf5KCtIPaFib4XaA.gif" height=250> 

</details>

<details>
    <summary>Hint2</summary>
Check high-pass filtering in <a href="https://learn-eu-central-1-prod-fleet01-xythos.content.blackboardcdn.com/60e83182c0bd4/35918417?X-Blackboard-S3-Bucket=learn-eu-central-1-prod-fleet01-xythos&X-Blackboard-Expiration=1696474800000&X-Blackboard-Signature=aDCpSR5cIS%2FlTC%2FwIrbm0XL61DeBtx9p0o1nS09OdbE%3D&X-Blackboard-Client-Id=113292&X-Blackboard-S3-Region=eu-central-1&response-cache-control=private%2C%20max-age%3D21600&response-content-disposition=inline%3B%20filename%2A%3DUTF-8%27%27Majid03-COMS30030-W2.pdf&response-content-type=application%2Fpdf&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEEUaDGV1LWNlbnRyYWwtMSJGMEQCIQCBuEzt5v%2BJBc9AfpGSAm2QwMkMZyQqeLgpa7%2BftrIODwIfGEXVANiynqSJFeU9Yf95IFKLX8K9oJka%2B7dhf2j60yq%2BBQhOEAMaDDYzNTU2NzkyNDE4MyIMKulsw%2BSANqSzMKrvKpsFLHihzCu%2FEn1UfQrAzCKrrrHNGOnrtB4cIdQCCYgvqouGlQDNWODwhawkW19hJu4a6xN3YZVRQcfYtxLYcrmEUWZ2BjubxqM81KTJPqHN2Dai0z27axCqWuIaeKRu3REML6vzslhF7502LtbIHSwnYFs80eI8dGH646v2dQPZKsV5jH421K93DPjQtlRL1Hb2r%2BajSPnf6lQyMNRJX3weOVpYe5ATRmFkFXAE4uira3EM%2F1ULZlOU6PSVJhwz61wANc3jbaxfTMxXK2CvbHCIAQz4PDLtrpCS5SirfWsU7q40irOcdCHK7EouMTiMtQOZ%2BSywbRnr2q6shWydaia7Cc4nJPJy52G1gazLDBctiuttL2XbHM3YW1Nrq14MJ9F8rDk66uzmzlbJTc6wDsvKbqUOfPmY3Ah9rvgnUwV8bYjSdBOjzxqDI61vuo4Y1vmfL1T%2FhV3O%2BgWGB93jc9hDBLuTl34xYkbNkk5Rh9N%2FFg8bSdsta38GwsF75L8J%2F7y3BmFDwuWyc2it8eHr2J%2B9vCIHUcjlVpteFi5g0SUIAznYkJN0syW%2FHP1JrN0Bz%2FMsW3w0g4hCGKS4pCJIwKVYn9b%2Fo6CWxLDrP4cJ5pPrWnCHLT47apC6A6QftnpRGiLLrcf9BmbUDdYqo4Oi9IUqDjvH3cR9fLhPuJcYggO7dtJS382nlo3UzJvNSKxOeVnBIe4C32cm419%2Fh1MDc9A4%2BS%2BbQPfLbT8HrI0BCsVwLOJJhADgWHTICMq2DpCpdqmuNiKb8YUVfOprQrmrvI9NrDjYUMUTm5Go9XgHQRl9togbI22vr8EZUV96wgiWg6IGlHuZQUJPVZ%2BwWucwFLEHmI9gQmW04BNItTXa47vOcN3PBeAAetnCEtn5NzCDp%2FeoBjqyAewBf2Qfv87eF7JSYudeSAu1DSbfwgEPOIo0LdLw0wTC46Sa1jvbTvVE51mt8vvAJfEpTiZQ8BsRiC%2BKJP%2BVNq8JJ%2FZ3BrB1w77zQLmDiKIWai52yIXMkF0azJ9I1IxD48BPKVEEtklMsQz%2Fv3KwqAN29QTBf8KkiUT%2BN3t2Sryrbma5Bzf8ikh0bQ41M6%2FMiUiXH1sv5ndVwIuXRIN%2FZJUdR8pagCfFdHx0MnMJ2KRHwUA%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20231004T210000Z&X-Amz-SignedHeaders=host&X-Amz-Expires=21600&X-Amz-Credential=ASIAZH6WM4PL4USZVOWY%2F20231004%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Signature=ed323a933f8ff6745ee5c8566e9642b9b0abf6692c09081747a126dcbbb6e5fd"  target="_blank">Lecture 03 - Filtering in Spatial Domain, page 8 Spatial Low/High Pass Filtering</a>
    
</details>

# The Number Plate Challenge

**Introduction**:
Image filtering techniques have a wide field of application. For instance, the compensation of image defects/corruption, also known as ‘image restoration’, which is one of many key areas where filtering is applied to solve problems in the real world. In this lab task you will use classical filtering techniques to enhance or recover seemingly ‘lost’ image information of interest.

**Overview**:
In particular, your task will be to recover number plate information from corrupted imagery by applying image filters in OpenCV that counter-act the corruptive processes (e.g. blur, noise) that the images have undergone. There are many ways to implement filters, if you want some inspiration from first principles, have a look at the code examples provided on the unit webpage to help you along…

## Task 2: Recovery by Sharpening

- The first number plate image has been captured by a camera that is slightly out of focus resulting in blur. 
- Your first task is to implement sharpening using OpenCV (for instance by modifying the provided filtering code) to recover the number plate. 
- Consider sharpening your image by adding the image to itself and subtracting a blurred version of it (i.e. perform **unsharp masking**).  Why and how does this technique work? 
- Make sure you avoid out-of-range problems and range shifts, since convolution may produce negative values and large ranges! 
- What effect do different kernel sizes and/or multiple rounds of filtering have on the number plate readability? 
- You won’t get a perfectly sharp image, but should aim at arriving at a sharpened image where the number is clearer than in the original.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/car1.png" height=150> 

<details>
    <summary>Hint</summary>
$I_\text{Sharpen} = I_\text{Original} + \alpha \left(I_\text{Original} - \text{Smooth}(I_\text{Original})\right)$

(See <a href="https://learn-eu-central-1-prod-fleet01-xythos.content.blackboardcdn.com/60e83182c0bd4/35918417?X-Blackboard-S3-Bucket=learn-eu-central-1-prod-fleet01-xythos&X-Blackboard-Expiration=1696474800000&X-Blackboard-Signature=aDCpSR5cIS%2FlTC%2FwIrbm0XL61DeBtx9p0o1nS09OdbE%3D&X-Blackboard-Client-Id=113292&X-Blackboard-S3-Region=eu-central-1&response-cache-control=private%2C%20max-age%3D21600&response-content-disposition=inline%3B%20filename%2A%3DUTF-8%27%27Majid03-COMS30030-W2.pdf&response-content-type=application%2Fpdf&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEEUaDGV1LWNlbnRyYWwtMSJGMEQCIQCBuEzt5v%2BJBc9AfpGSAm2QwMkMZyQqeLgpa7%2BftrIODwIfGEXVANiynqSJFeU9Yf95IFKLX8K9oJka%2B7dhf2j60yq%2BBQhOEAMaDDYzNTU2NzkyNDE4MyIMKulsw%2BSANqSzMKrvKpsFLHihzCu%2FEn1UfQrAzCKrrrHNGOnrtB4cIdQCCYgvqouGlQDNWODwhawkW19hJu4a6xN3YZVRQcfYtxLYcrmEUWZ2BjubxqM81KTJPqHN2Dai0z27axCqWuIaeKRu3REML6vzslhF7502LtbIHSwnYFs80eI8dGH646v2dQPZKsV5jH421K93DPjQtlRL1Hb2r%2BajSPnf6lQyMNRJX3weOVpYe5ATRmFkFXAE4uira3EM%2F1ULZlOU6PSVJhwz61wANc3jbaxfTMxXK2CvbHCIAQz4PDLtrpCS5SirfWsU7q40irOcdCHK7EouMTiMtQOZ%2BSywbRnr2q6shWydaia7Cc4nJPJy52G1gazLDBctiuttL2XbHM3YW1Nrq14MJ9F8rDk66uzmzlbJTc6wDsvKbqUOfPmY3Ah9rvgnUwV8bYjSdBOjzxqDI61vuo4Y1vmfL1T%2FhV3O%2BgWGB93jc9hDBLuTl34xYkbNkk5Rh9N%2FFg8bSdsta38GwsF75L8J%2F7y3BmFDwuWyc2it8eHr2J%2B9vCIHUcjlVpteFi5g0SUIAznYkJN0syW%2FHP1JrN0Bz%2FMsW3w0g4hCGKS4pCJIwKVYn9b%2Fo6CWxLDrP4cJ5pPrWnCHLT47apC6A6QftnpRGiLLrcf9BmbUDdYqo4Oi9IUqDjvH3cR9fLhPuJcYggO7dtJS382nlo3UzJvNSKxOeVnBIe4C32cm419%2Fh1MDc9A4%2BS%2BbQPfLbT8HrI0BCsVwLOJJhADgWHTICMq2DpCpdqmuNiKb8YUVfOprQrmrvI9NrDjYUMUTm5Go9XgHQRl9togbI22vr8EZUV96wgiWg6IGlHuZQUJPVZ%2BwWucwFLEHmI9gQmW04BNItTXa47vOcN3PBeAAetnCEtn5NzCDp%2FeoBjqyAewBf2Qfv87eF7JSYudeSAu1DSbfwgEPOIo0LdLw0wTC46Sa1jvbTvVE51mt8vvAJfEpTiZQ8BsRiC%2BKJP%2BVNq8JJ%2FZ3BrB1w77zQLmDiKIWai52yIXMkF0azJ9I1IxD48BPKVEEtklMsQz%2Fv3KwqAN29QTBf8KkiUT%2BN3t2Sryrbma5Bzf8ikh0bQ41M6%2FMiUiXH1sv5ndVwIuXRIN%2FZJUdR8pagCfFdHx0MnMJ2KRHwUA%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20231004T210000Z&X-Amz-SignedHeaders=host&X-Amz-Expires=21600&X-Amz-Credential=ASIAZH6WM4PL4USZVOWY%2F20231004%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Signature=ed323a933f8ff6745ee5c8566e9642b9b0abf6692c09081747a126dcbbb6e5fd"  target="_blank">Lecture 03 - Filtering in Spatial Domain, page 29 Sharpening</a>).
</details>

## Task 3: Recovery by Median Filtering

- The second number plate was captured on film material of very poor quality resulting in ‘salt and pepper’ noise. 
- Your task is to implement a median filter to recover the number plate information. 
- A median filter operates by replacing a pixel with the median of ‘its neighbouring pixels and the pixel itself’. 
- What influence does the size of the pixel neighbourhood have (e.g. 8 adjacent pixels, 24 neighbouring pixels) on the number plate readability?

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/car2.png" height=150> 

## Task 4: OPTIONAL: Recovery by De-Convolution

- This task is optional and advanced, it should be attempted only if you who have finished task 1 and 2 fully. 
- The third number plate is distorted by motion blur. 
- To recover the number plate you may want to use **Wiener Deconvolution**. 
- First, familiarise yourself with the idea of this filter (see below). 
- We have provided you with a Wiener deconvolution function in `deconvolution.py`.
- You need to experiment with the blur length, blur angle and signal to noise ratio to try and get a good reconstruction. 
- Have a close look at the blurred image to help you estimate these parameters.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/car3.png" height=150>

<details>
    <summary>Hint</summary>
Adjust this function call `recover = WienerDeconvoluition(gray_image,15,3,0.001,0)`
</details>

### Wiener De-Convolution

**Idea**: Restore an image by convolution with an adjusted inverse kernel that estimates the loss of information per frequency.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/Wiener%20De-Convolution.png" height=250> 

## Task 5: OPTIONAL: Long-exposure Photography

- Long-exposure photography involves using a long-duration shutter speed. However, in many situations a long-duration shutter speed causes too many highlights on the image (overexposure).
- This task will let you explore how your phone creates this effect without overexposure.
- A 1-second waterfall clip (at 30 fps) has been extracted to 30 frames in `img/waterfall`.
- Think about how to make this smooth effect using these 30 frames.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/waterfall.gif" height=250> &rarr; <img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/longexposure.jpg" height=250>

## Task 6: OPTIONAL: Remove Tourists

- Often, taking photos of tourist attractions without people is impossible.
- In this task, you will process multiple images taken in slightly different times at the same landmark. People appear at different locations in the images. 
- How can you use a simple filter to produce a single image without people from eight images, provided in `img/landmark`.

<img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/landmark/img1.jpg" height=250> <img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/landmark/img2.jpg" height=250> &rarr; <img src="https://github.com/UoB-CS-IPCV/Lab2-number-plate-challenge/blob/main/img/landmark.jpg" height=250>  
