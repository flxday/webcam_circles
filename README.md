# webcam_circleis
Circle detection from online webcam images

The Hough Transform works

The Hough transform is a transformation used to detect straight lines.
The lines in the Hough transform are expressed in Polar System.
Monitor the intersection between the curves of each image point is made.

If the number of intersections is above a "threshold", then it is declared as a line with parameters (0, r0) of the intersection point.
OpenCV implements two types of the Hough transform

The standard Hough Transform 

In OpenCV it is implemented with HoughLines function.

Line Probabilistic Hough Transform.

A more efficient implementation of Hough transform. the ends of the lines detected is output.

In OpenCV it is implemented with HoughLinesP function

-Gray scale image
        cv::cvtColor(image, gray_image, CV_BGR2GRAY); 
        
-Detect edges using a Canny detector
        Canny (src, dst, 50, 200, 3); 
        
-Probabilistic Transform line Hough
        vector<Vec3f> lines; 
        HoughLinesP( image, lines, 1, CV_PI/180, 80, 30, 10 ); 
        
with the arguments:
dst: Output of the edge detector. It should be a grayscale image (although in fact it is a binary one) 
lines: A vector that will store the parameters  of the detected lines 
rho : The resolution of the parameter  in pixels. We use 1 pixel. 
theta: The resolution of the parameter  in radians. We use 1 degree (CV_PI/180) 
threshold: The minimum number of intersections to “detect” a line 
minLinLength: The minimum number of points that can form a line. Lines with less than this number of points are disregarded. 
maxLineGap: The maximum gap between two points to be considered in the same line. 


-Shows the result drawing the lines.
        for( size_t i = 0; i < lines.size(); i++ ) 
        { 
        line( gray_image, Point(lines[i][0], lines[i][1]), 
            Point(lines[i][2], lines[i][3]), Scalar(0,0,255), 3, 8 ); 
        }

http://docs.opencv.org/2.4/modules/imgproc/doc/feature_detection.html
http://docs.opencv.org/2.4/doc/tutorials/imgproc/imgtrans/hough_lines/hough_lines.html
