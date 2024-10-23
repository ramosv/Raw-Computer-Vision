# Computer Vision no libraries
## Assignment 1


### Assignment Report

For this assignment, you will have to write the code without the use of computer vision libraries
(other than to use functions to read and write images).
You can implement the assignment in any programming language. Submit your code in addition
to the assignment report. The assignment can be completed in teams of two.

### Assignment Report

1. Choose an 8-bit colored image and convert it to a grayscale image. Explain your approach and show the input and output image.

By manupulating the RBG values, we can turn an 8-bit color image into its greyscale interpretatnion. RBG values are represented as an 8-bit interger. We can multiply each RBG pixel by spefic decimal value to force the pixel to fall within the greyscale range. We were able to achieve this by using a weighted sum on the pixel value, that modifies each RBG component to transform to its greyscale interpreation.

Formula that we use to modify each pixel:
`gray_value = int(0.299 * r + 0.587 * g + 0.114 * b)`

Then we looped through the height and width allowing us to target each pixel and apply our formula.

The result was a greyscale representation of the orginal image.

For this problem and for furure problems we stared off by using images from the cifar-10 dataset. We wanted the ability to test several images quickly without having to download and upload a large set of image files.

-Vicente

2. Add white gaussian noise to the grayscale image. Show the effects of the noise when
the standard deviation is 1, 10 and 30 and 50.

In this task, we first added White Gaussian noise to a grayscale image with varying standard deviations (1, 10, 30, and 50). When tested, low standard deviations 1 and 10 had minimal noise, causing slight distortion while maintaining the image structure. However, with higher values 30 and 50, the noise became overwhelming, significantly lowering the image quality

-June

3. Add Salt and Pepper noise to 10% and 30% of the pixels in the grayscale image in 1.
Salt and Pepper noise is added to an image by adding random bright and random dark
pixels all over the image.

By applying a similar approach to problem 1, we can iterate through the image allowing to target each pixel individually. Random pixels will be selected to be turned completly white or complteley black. Again by modifying the RBG value at each pixel. The result is an image whith a randomized set of pixels that have been turned to white and black.

-Vicente

4. Implement a Box Filter, Median Filter and Gaussian Filter to remove the white gaussian
noise with standard deviation 50 and the Salt and Pepper noise at 30%. Let the kernel
size be 3 x 3. Explain your choice of other parameters and any non-trivial steps in your
implementation (e.g., how did you handle the borders in the image).

After introducing Gaussian noise (σ = 50) and Salt-and-Pepper noise at 30%, we applied three different filters. Box Filter, Median Filter, and Gaussian Filter—with a 3x3 kernel to reduce the noise. The Box Filter, which computes the average of neighboring pixels, effectively reduced the Gaussian noise but caused significant blurring and was less effective on Salt-and-Pepper noise. The Median Filter, which replaces each pixel with the median of its neighborhood, was particularly effective at removing Salt-and-Pepper noise, preserving the edges and structure of the image. The Gaussian Filter, which applies a weighted average, worked best for Gaussian noise, smoothing it effectively while maintaining the image's details, but performed poorly with Salt-and-Pepper noise. In all cases, we handled the image borders by using the "reflect" padding method to ensure the filtering process covered the entire image without introducing artifacts at the edges. Each filter had its strengths, with the Median Filter excelling at Salt-and-Pepper noise and the Gaussian Filter being more suited for Gaussian noise.

-June

5. Vary the kernel size to 5 x 5 and 10 x 10 and show its effect on the output image

By incresing the size of the kernel to 5x5 and 10x10, the effect highlighted on question 4 were significatly more noticible. In the 5x5 kernel salt and peperand test, we only saw 1 or 2 pixels that still had some salt/peper left. And with the 10x10 kernels, we did not see a single salt and pepper pixel. Testing the filter with our original gaussian filter showed a significant increase in the blur effect, making the image completely udentefiably for the 32x32 pixel car image. Due to the larger pixel size of our cat image. We were able to see increased blurredness but still perseved it the shape and looks of the orignal. By modifying the kernel size we size an increse of the effect identified during question 4, with more adverse effect on the image with larger kernel size.

-Vicente