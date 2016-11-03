# webcam_circleis
Circle detection from online webcam images

The Hough Transform works

The Hough transform is a transformation used to detect straight lines.
The lines in the Hough transform are expressed in Polar System.
Monitor the intersection between the curves of each image point is made.

If the number of intersections is above a "threshold", then it is declared as a line with parameters (0, r0) of the 

The standard Hough Transform 

In OpenCV it is implemented with HoughLines function.

Line Probabilistic Hough Transform.

A more efficient implementation of Hough transform. the ends of the lines detected is output.

In OpenCV it is implemented with HoughLinesP function

HoughCircles

Finds circles in a grayscale image using the Hough transform.

C++: void HoughCircles(InputArray image, OutputArray circles, int method, double dp, double minDist, double param1=100, double param2=100, int minRadius=0, int maxRadius=0 )

C: CvSeq* cvHoughCircles(CvArr* image, void* circle_storage, int method, double dp, double min_dist, double param1=100, double param2=100, int min_radius=0, int max_radius=0 )

Python: cv2.HoughCircles(image, method, dp, minDist[, circles[, param1[, param2[, minRadius[, maxRadius]]]]]) → circles
    Parameters:	

        image – 8-bit, single-channel, grayscale input image.
        circles – Output vector of found circles. Each vector is encoded as a 3-element floating-point vector (x, y, radius) .
        circle_storage – In C function this is a memory storage that will contain the output sequence of found circles.
        method – Detection method to use. Currently, the only implemented method is CV_HOUGH_GRADIENT , which is basically 21HT , described in [Yuen90].
        dp – Inverse ratio of the accumulator resolution to the image resolution. For example, if dp=1 , the accumulator has the same resolution as the input image. If dp=2 , the accumulator has half as big width and height.
        minDist – Minimum distance between the centers of the detected circles. If the parameter is too small, multiple neighbor circles may be falsely detected in addition to a true one. If it is too large, some circles may be missed.
        param1 – First method-specific parameter. In case of CV_HOUGH_GRADIENT , it is the higher threshold of the two passed to the Canny() edge detector (the lower one is twice smaller).
        param2 – Second method-specific parameter. In case of CV_HOUGH_GRADIENT , it is the accumulator threshold for the circle centers at the detection stage. The smaller it is, the more false circles may be detected. Circles, corresponding to the larger accumulator values, will be returned first.
        minRadius – Minimum circle radius.
        maxRadius – Maximum circle radius.

http://docs.opencv.org/2.4/modules/imgproc/doc/feature_detection.html


