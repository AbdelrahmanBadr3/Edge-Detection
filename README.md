# Edge-Detection
## Integral Image and Local Sum Calculation
-  ### CalculateIntegral
    - Input: 2D array representing the image (feel free to use a predefined function to transform an image into an array).
    - Output: 2D array representing the integral image.

-  ### CalculateLocalSum
    - Input: An integral image, and a two pairs of coordinates (𝑝0 = (𝑥0, 𝑦0), 𝑝1 = (𝑥1, 𝑦1)).
    - Output: The local sum for the rectangular area defined by the pair of points (as 𝑝0 being the upper left corner, and 𝑝1 being the lower right corner of this rectangular area).
## Kernel Convolution
### Kernels Structure
-   ### FirstDerivativeDetector
    - Prewitt edge detector: h1 and h2 (horizontal and vertical, respectively) are to be convolved. For kernel size 𝑛 x 𝑛 (𝑛 is odd), both kernels are structured as:
    - 1’s for upper half of h1and right half of h2
    - 0’s for the middle row of h1and the middle column of h2
    - −1’s for bottom half of h1and left half of h2

-   ### SecondDerivativeDetector
    - Laplace edge detector: for kernel size 𝑛 x 𝑛 (𝑛 is odd), the kernel is structuredas:
    - 𝑛2 − 1 for the middle cell
    - −1’s elsewhere

-   ### MeanAverage
    - For kernel size 𝑛 x 𝑛 (𝑛 is odd), the kernel is structured as:
    - 1/𝑛2 all over the kernel area
##  Functions
- ### EdgeDetect
    - Input: 2D array representing the integral image of an input image, and kernel size to be convolved.
    - Output: A pair of 2D arrays representing edges detected using the first and the second derivatives.
    - Description: The first output is a 2D array that contains the magnitude values of the first derivative detector using h1 and h2 as shown in class. The second output is a 2D array that contains the absolute values of the magnitudes of the second derivative kernel.
- ### RefineEdge
    - Input: 2D array 𝑖𝑖, kernel size 𝑠, and ratio 𝑟.
    - Output: 2D array containing the refined edges.
    - Description: 𝑖𝑖 is the integral image of the edge detection result. For each pixel
in the output image: 
        ```
        if (𝐼(𝑥, 𝑦) > 𝜇𝑠(𝑥, 𝑦) ∗ 𝑟):
            𝐼′(𝑥, 𝑦) = 𝑖𝑖(𝑥, 𝑦)
        else:
            𝐼′(𝑥, 𝑦) = 0
        ```

       
