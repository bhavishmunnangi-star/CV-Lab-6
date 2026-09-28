CV Lab 6 — Edge Detection Using OpenCV
📌 Overview

This project demonstrates three commonly used edge detection techniques in Computer Vision:

Sobel Edge Detection

Prewitt Edge Detection

Canny Edge Detection

The program loads a grayscale strawberry image, applies each edge detection method, and displays the results side-by-side for comparison.

🛠️ Technologies Used

Python

OpenCV (cv2)

NumPy

Matplotlib

Google Colab

📂 Input Image

The program expects an image named:

strawberry.jpg


located at:

/content/strawberry.jpg


The image is loaded in grayscale mode before applying the edge detection techniques.

🔍 Edge Detection Methods
1. Sobel Edge Detection

The Sobel operator calculates the image gradient in both the horizontal and vertical directions.

sobelx = cv2.Sobel(img, cv2.CV_64F, 1, 0, ksize=3)
sobely = cv2.Sobel(img, cv2.CV_64F, 0, 1, ksize=3)


The horizontal and vertical gradients are combined to obtain the overall edge magnitude.

2. Prewitt Edge Detection

The Prewitt operator uses two 3×3 kernels to detect horizontal and vertical edges.

kernelx = np.array([
    [-1, 0, 1],
    [-1, 0, 1],
    [-1, 0, 1]
])

kernely = np.array([
    [-1, -1, -1],
    [0, 0, 0],
    [1, 1, 1]
])


The two filtered images are combined to produce the final Prewitt edge image.

3. Canny Edge Detection

Canny edge detection is applied using OpenCV's built-in function:

canny_edges = cv2.Canny(img, 100, 200)


The threshold values used are:

Lower threshold: 100

Upper threshold: 200

📊 Output

The program displays four images in a 2×2 layout:

Position	Image
1	Original grayscale image
2	Sobel edge detection
3	Prewitt edge detection
4	Canny edge detection

The output allows visual comparison of the edges detected by each technique.

▶️ How to Run
Using Google Colab

Open the notebook in Google Colab.

Upload strawberry.jpg to the /content/ directory.

Run all the cells.

The comparison of the three edge detection methods will be displayed.

Using Python Locally

Install the required libraries:

pip install opencv-python numpy matplotlib


Place strawberry.jpg in the appropriate location and update the image path if necessary.

Then run the Python script.

📁 Project Structure
CV-Lab-6/
│
├── strawberry.jpg
├── CV_Lab_6.py
└── README.md

🎯 Objective

The objective of this experiment is to understand and compare different edge detection techniques used in digital image processing and computer vision.

📝 Conclusion

Sobel, Prewitt, and Canny are useful techniques for detecting edges in images. Sobel and Prewitt use gradient-based kernels, while Canny uses multiple processing stages to produce well-defined edges. Comparing their outputs helps demonstrate how different edge detection methods respond to image boundaries and details.
