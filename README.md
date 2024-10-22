# Computer Vision no libraries
## Assignment 1


### Assignment Report

For this assignment, you will have to write the code without the use of computer vision libraries
(other than to use functions to read and write images).
You can implement the assignment in any programming language. Submit your code in addition
to the assignment report. The assignment can be completed in teams of two.

### Assignment Report

1. Choose an 8-bit colored image and convert it to a grayscale image. Explain your
approach and show the input and output image.

-Vicente

2. Add white gaussian noise to the grayscale image. Show the effects of the noise when
the standard deviation is 1, 10 and 30 and 50.

In this task, we first added White Gaussian noise to a grayscale image with varying standard deviations (1, 10, 30, and 50). When tested, low standard deviations 1 and 10 had minimal noise, causing slight distortion while maintaining the image structure. However, with higher values 30 and 50, the noise became overwhelming, significantly lowering the image quality

-June

1. Add Salt and Pepper noise to 10% and 30% of the pixels in the grayscale image in 1.
Salt and Pepper noise is added to an image by adding random bright and random dark
pixels all over the image.

-Vicente

4. Implement a Box Filter, Median Filter and Gaussian Filter to remove the white gaussian
noise with standard deviation 50 and the Salt and Pepper noise at 30%. Let the kernel
size be 3 x 3. Explain your choice of other parameters and any non-trivial steps in your
implementation (e.g., how did you handle the borders in the image).

After introducing Gaussian noise (σ = 50) and Salt-and-Pepper noise at 30%, we applied three different filters. Box Filter, Median Filter, and Gaussian Filter—with a 3x3 kernel to reduce the noise. The Box Filter, which computes the average of neighboring pixels, effectively reduced the Gaussian noise but caused significant blurring and was less effective on Salt-and-Pepper noise. The Median Filter, which replaces each pixel with the median of its neighborhood, was particularly effective at removing Salt-and-Pepper noise, preserving the edges and structure of the image. The Gaussian Filter, which applies a weighted average, worked best for Gaussian noise, smoothing it effectively while maintaining the image's details, but performed poorly with Salt-and-Pepper noise. In all cases, we handled the image borders by using the "reflect" padding method to ensure the filtering process covered the entire image without introducing artifacts at the edges. Each filter had its strengths, with the Median Filter excelling at Salt-and-Pepper noise and the Gaussian Filter being more suited for Gaussian noise.

-June

1. Vary the kernel size to 5 x 5 and 10 x 10 and show its effect on the output image

-Vicente