/*
Title: Open CV with Python
Decription: Open CV with Python
Author: Bhaskar Mangal
Date: 
Tags: Open CV with Python
*/

https://stackoverflow.com/questions/13685771/opencv-python-calcopticalflowfarneback

https://www.quora.com/What-is-the-reason-Lena-S%C3%B6derbergs-photo-is-used-widely-to-test-algorithms-in-image-processing

* Conceptually, a byte is an integer ranging from 0 to 255. Throughout real-time graphics applications today, a pixel is typically represented by one byte per channel, though other representations are also possible.
* An OpenCV image is a 2D or 3D array of type numpy.array
* An 8-bit grayscale image is a 2D array containing byte values.
* A 24-bit BGR image is a 3D array, also containing byte values.

* We may access these values by using an expression like image[0, 0] or image[0, 0, 0].
  - The first index is the pixel's y coordinate, or row, 0 being the top.
  - The second index is the pixel's x coordinate, or column, 0 being the leftmost.
  - The third index (if applicable) represents a color channel.