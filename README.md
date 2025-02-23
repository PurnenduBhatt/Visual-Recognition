# Visual-Recognition
Detailed Report on Image Processing and Stitching Project
Overview
This project involves two key tasks:
    1. Coin Detection and Segmentation (Part 1) – Detecting and counting coins in an image.
    2. Image Stitching (Part 2) – Combining multiple images into a panorama.
The implementation relies on OpenCV and NumPy for image processing and feature extraction.

Part 1: Coin Detection and Segmentation
Objective
    • Detect and count coins from an image using image processing techniques.
    • Highlight detected coins with bounding rectangles.
Implementation Details
The script (part1.py) follows these steps:
    1. Image Preprocessing:
        ◦ Converts the input image to grayscale (cv2.cvtColor).
        ◦ Applies Gaussian Blur (cv2.GaussianBlur) to reduce noise and improve edge detection.
    2. Thresholding:
        ◦ Uses Adaptive Thresholding (cv2.adaptiveThreshold) to create a binary mask for coins.
        ◦ This method ensures robust detection under varying lighting conditions.
    3. Noise Removal:
        ◦ Uses Morphological Operations (cv2.morphologyEx) to eliminate small noise.
        ◦ This helps in obtaining cleaner object boundaries.
    4. Contour Detection:
        ◦ Extracts object boundaries using cv2.findContours.
        ◦ Filters out small areas to avoid detecting unnecessary objects.
    5. Coin Counting & Highlighting:
        ◦ Draws bounding rectangles (cv2.boundingRect) around detected coins.
        ◦ Counts the total number of coins.
    6. Output Generation:
        ◦ Saves the processed image (detected_coins.jpg).
        ◦ Displays the result using cv2_imshow (Google Colab-specific).


Part 2: Image Stitching
Objective
    • Stitch multiple images together to create a panoramic image.
Implementation Details
The image stitching is handled using two scripts:
    1. stiching.py – Loads images and calls the stitching process.
    2. panorama.py – Implements the panorama stitching algorithm.
Process Breakdown
1. Image Loading & Preprocessing (stiching.py)
    • Reads user-defined image paths.
    • Resizes images to maintain a consistent aspect ratio.
2. Feature Detection & Matching (panorama.py)
    • Uses SIFT (Scale-Invariant Feature Transform) to detect keypoints.
    • Matches features using BruteForce matcher with Lowe’s ratio test.
3. Homography Computation & Image Warping
    • Finds the transformation matrix using cv2.findHomography.
    • Warps images into alignment using cv2.warpPerspective.
4. Image Blending & Output Generation
    • Merges images using homography transformations.
    • Displays the keypoint matches and final stitched panorama.
    • Saves output images (panorama_image.jpg & matched_points.jpg).





