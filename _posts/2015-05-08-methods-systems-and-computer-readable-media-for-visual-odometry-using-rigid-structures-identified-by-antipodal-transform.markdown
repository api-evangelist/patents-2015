---

title: Methods, systems, and computer readable media for visual odometry using rigid structures identified by antipodal transform
abstract: The subject matter described herein includes methods for visual odometry using rigid structures identified by an antipodal transform. One exemplary method includes receiving a sequence of images captured by a camera. The method further includes identifying rigid structures in the images using an antipodal transform. The method further includes identifying correspondence between rigid structures in different image frames. The method further includes estimating motion of the camera based on motion of corresponding rigid structures among the different image frames.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09280832&OS=09280832&RS=09280832
owner: The Trustees of the University of Pennsylvania
number: 09280832
owner_city: Philadelphia
owner_country: US
publication_date: 20150508
---
This application claims the benefit of U.S. Provisional Patent Application Ser. No. 61 990 478 filed May 8 2014 the disclosure of which is incorporated herein by reference in its entirety.

This invention was made with government support under Grant No. 0835714 awarded by the National Science Foundation. The government has certain rights in the invention.

The subject matter described herein relates to visual odometry. More particularly the subject matter described herein relates to methods systems and computer readable media for visual odometry using rigid structures identified by antipodal transform.

Visual odometry refers to the estimation of the path of a camera from solely from video images taken by the camera. The term visual odometry was created by Nister due to its similarity to wheel odometry. Wheel odometry estimates the distance traveled by a vehicle based on rotations of the vehicle s wheels. Visual odometry estimates motion not only the distance traveled but also the path or trajectory X Y Z coordinates and camera orientation at each point traveled by a camera based on analysis of images captured by a camera in successive video frames. Such a path or trajectory can be used to re trace the path of the camera or the object to which the camera is attached. Applications of video odometry include robotics location services turn by turn navigation and augmented reality. For example if GPS communications are not available visual odometry can provide a trajectory to be followed if it is desirable to retrace a path.

Existing visual odometry algorithms rely on a triangulation step in order to reconstruct tracked features. The reconstructed features are then tracked between video sequences in order to maintain a uniform scale of camera trajectory. Reconstructing tracked features using triangulation for each frame is computationally intensive. Accordingly there exists a need for improved methods for visual odometry that avoids or reduces the need for triangulation for each frame and is less computationally intensive than existing visual odometry methods.

The subject matter described herein includes methods for visual odometry using rigid structures identified by an antipodal transform. The method further includes identifying correspondence between rigid structures in different image frames. One exemplary method includes receiving a sequence of images captured by a camera. The method further includes identifying rigid structures in the images using an antipodal transform. The method further includes estimating motion of the camera based on motion of corresponding rigid structures among the different image frames.

The subject matter described herein can be implemented in software in combination with hardware and or firmware. For example the subject matter described herein can be implemented in software executed by a processor. In one exemplary implementation the subject matter described herein can be implemented using a non transitory computer readable medium having stored thereon computer executable instructions that when executed by the processor of a computer control the computer to perform steps. Exemplary computer readable media suitable for implementing the subject matter described herein include non transitory computer readable media such as disk memory devices chip memory devices programmable logic devices and application specific integrated circuits. In addition a computer readable medium that implements the subject matter described herein may be located on a single device or computing platform or may be distributed across multiple devices or computing platforms.

The subject matter described herein includes methods systems and computer readable media for visual odometry using rigid structures identified by antipodal transform. Rather than using a triangulation step to reconstruct tracked features in each frame to maintain a uniform scale of camera trajectory the subject matter described herein records the scale of tracked features to determine translation of the camera. An exemplary process for visual odometry using rigid structures identified by antipodal transforms will now be described.

As stated above visual odometry is the estimation of the trajectory of motion of a camera using video as input. This trajectory is with respect to an initial coordinate system and can be visualized as a path of X Y Z coordinates in space.

The subject matter described herein includes a new approach for the computation of visual odometry based on a hybrid system using both points and line segments detected and tracked in images of the video. The present approach encompasses the following steps 

The antipodal transform is closely related to the Distance Transform in that it applies a score to binary matrix elements based on their relationship to the closest occupied element and occupancy matrices where this some distinct range of scores for all elements. The subject matter described herein used the antipodal transform to identify rigid structures in image data where a rigid structure is a structure such as doors windows walls frames furniture or other fixed structures that do not change from scene to scene that is not likely to change from one image frame to the next. Maxima and minima of the transform are used to find key points of interest in a scene where key points will be tracked between frames. The antipodal transform biases pixels corresponding with rigid physical structures in the scene environment.

There are a number of other applications for the antipodal transform. In digital image processing the transform can be used to determine blurring effects and also for skeletonizing. The transform signature itself as well as structural correspondence between key points in a scene can be used in object detection. In robotics where a matrix may correspond to a map where values correspond to the level or obstacles in the terrain the transform may be applied in motion planning or path finding.

In contour analysis and segmentation a gradient contour is often discovered by tracing an edge until a loop closure. The centroid of the contour can then be found by taking the mean of the positions of the boundary pixels. However the antipodal transform directly computes the position of the center of gradient contours. Further contours can be extracted by taking the region around an Antipodal Transform maxima and minima.

As stated above the antipodal transform is similar to the distance transform. In the distance transform given a binary matrix the score of each point is its distance to the nearest occupied element in the matrix. The antipodal transform can also be expressed as a computation over an occupancy matrix. Each point is given a score dependent on the distance of the closest occupied element in one particular direction minus the distance of the closest element in the opposite direction

The antipodal transform is defined for a given point as the sum of all distances of the closest point in a particular direction minus the point closest point in the opposite direction for all directions. In our fast computation approach we apply this summation solely along the vertical and horizontal directions in order to increase computation speed. See examples below 

GEMS defines a family of nested feature descriptors that use the gradient magnitude. The gradient magnitude for a given pixel is the difference in intensity from the pixel to a neighboring pixel. In one embodiment the gradient magnitude can be computed using the following expression 

Nested descriptors are defined by their pattern and binary structure. Nested descriptors access an image at various octaves and binarize elements against symmetrically placed elements within the structure pattern.

A spatial grid over a region of an image is applied at multiple scales. The mean of the gradient magnitude is computed in each grid space. Pairs of scales are binarized. Pairs of binarized scales are than subtracted from each other. This yields a ternarized vector 1 0 1.

The grid structure is composed of adjacent polygons or circles. The grid window as shown in is a rectangle but may be any symmetrical shape including a circle.

The Hamming distance or an alternate similarity metric may be used to determine the distance between feature descriptors. Hamming distance is the sum of the differences between each element in the vector.

A set of matches is maintained between frame sequences. For instance the closest matching descriptors to the features in the preceding image are found. After an outlier elimination step described below all matching points are kept. This is then repeated for the third frame in each frame triplet. As matched features between triplets are lost new features are added to the tracking set.

For each triplet one exemplary method for determining correspondence between frames utilizes a minimum of at least 5 points.

Once the gradients are determined the gradients may be used to determine line matching between images. illustrates an example of line matching between lines associated with GEM descriptors. In the left and right grids represent matching GEMS gradients in two different images.

A line is associated with a GEMS keypoint if any portion of its defining gradient is within the largest scale window. In the solid diagonal horizontal and vertical lines that are within the largest scale grid represent lines whose defining gradient is within the largest scale window. The dashed lines between the grids illustrate corresponding lines identified in the different images.

Three thresholds over line orientation angle are used to categorize the lines into three categories vertical horizontal and diagonal lines. Sets of lines associated with matching GEMS points are matched. Only lines categorized within similar orientations are matched. For vertical and diagonal lines lines are matched by the order of their midpoints along the horizontal axis. Horizontal lines are matched by the order of their midpoints along the vertical axis. The horizontal and vertical axis is with respect to the camera s optical axis.

The Levenberg Marquardt algorithm can be applied to match sets of lines within orientation categories instead of matching by the order of their midpoints.

Once correspondence between keypoints is identified outlier keypoints correspondences are filtered based on a heuristic consensus algorithm for matched feature points between two images. This method is applied across both pairs of images for a three frame sequence. Structure based outlier elimination will now be explained in more detail.

The structure based iterative outlier elimination process described hereinbelow may be used to eliminate outliers between feature matches in images. It is an alternative to the RANSAC Random Sample Consensus approach most popularly used. According to this approach N matched points in each respective frame are tracked. For all matched points within a frame the respective distance to all other matched points is computed. This builds a distance curve for each keypoint where order is determined by the closest matching feature vectors. The compiled keypoint curves for each image are then matched. After the curve match with the lowest error is found points with the highest individual error are removed.

In the right hand frame in the matched keypoints are and and the mismatched keypoint is . Thus the lines from to and to represent the distance from the mismatched keypoint to the matched points.

For each matched keypoint the relative distances to other matched keypoints are compiled and ordered by the closest matching feature descriptors. The curves computed for each image are matched. Iteratively one curve is moved forward and subtracted against the other. The position yielding the least error is found. The points corresponding to sections of the curve with the highest error are omitted from the match model.

The following equation illustrates the structure based iterative outlier elimination algorithm describe above with respect to 

Once correspondence between lines is identified and outliers matches are eliminated vanishing points can be identified from the remaining matching lines in a given frame and absolute rotation can be computed from the vanishing points. illustrates the identification of vanishing points in a scene.

If v v and vcorrespond to the matching vanishing points in each direction the rotation can be computed as 

If only two vanishing points are found in the scene the cross product of the normalized points can be computed in order to find the rotation matrix as follows 

Once corresponding features are identified between image frames the motion of the features can be used to determine camera rotation and movement between frames. The following steps describe the computation of camera rotation and movement between image frames.

The following sections describe line representation and the use of tracked lines in different image frames to determine camera rotation and movement between frames.

In order to determine camera rotation and movement between image frames line movement and rotation between image frames may be determined. Before movement and rotation can be determined lines in each image frame must be parameterized. illustrates exemplary parameterization of a line l. A line in space can be represented by the unit vector 1 parallel to the line and the momentum torque d with respect to the origin. Let X be a keypoint on the line. The moment vector reads then 1 1 

Let us assume m lines L 1 . . . m in 3D space captured by a camera in time points tand t . Let lby the projection of a line in the image. It is geometrically more intuitive instead of lto use the viewing plane as measurement spanned by the projection center Oand the line l. It can be proven that two frames are insufficient for a 3D interpretation.

We denote that 1 d the Pl cker coordinates of a line . We denote with nthe normal to the viewing plane at time t. This normal can be estimated directly from the line equation in the image plane where x and y represent axis in Cartesian coordinates and a b is the slope of the line 0. 3 and c is the y axis intercept.

We denote with Aand Bthe rotation from time tto time tand t respectively. We use same subscripts for the translations aand b. illustrates motion derived from a line tracked in three frames. Pl cker coordinates change then as follows 3.1 . 3.2 

If we eliminate 1 and d we obtain an equation with the only unknowns being the rotations and translations. 4 5 taking the vector product from left hand side and the right hand side. . 6 

This yields our geometric consistency equation for three frames with line correspondences which contains only rotations 0. 7 

First we compute the rotation matrices. This can be solved by iterative minimization. Next we are able to find two equations for translations which can be solved as a system of linear equations using the solved rotations from the previous step. To compute the translations we use the following equations 0 8 0. 9 . 10 

Referring to a system for vision supplemented localization may be implemented on a computing platform including a processor and a memory . Computing platform may be any suitable computing platform such as a personal computer a tablet a server or other computing platform including one or more hardware components. In the illustrated example memory may store instructions that are executed by processor for vision supplemented localization according to embodiments of the subject matter described herein. Accordingly memory more store a line and keypoint feature extractor that receives as input image frames and extracts line and keypoint features such as points and line segments from the image frames using the algorithms described above. Line and keypoint feature extractor may output the extracted line features to camera motion estimator . Camera motion estimator may estimate the motion of a camera using the line features and the algorithm described above.

Thus the subject matter described herein includes improved methods for visual odometry using the antipodal transform. The methods described herein improve the technological field of visual odometry by accurately identify feature correspondence between frames and with less computational resources required by convention methods. The methods described herein improve the functionality of a computer that computes visual odometry correspondences because less computational resources are required than with convention methods. A computer programmed with the visual odometry methods described herein thus constitutes a special purpose processing device with applications to navigation augmented reality robotics and other technological fields where tracking camera motion from video images captured by the camera is desirable.

The documents corresponding to each of the following citations is hereby incorporated herein in its entirety.

The following citations provided additional detail on the terms in parentheses preceding each citation and which appear in the description hereinabove. ICL 

It will be understood that various details of the presently disclosed subject matter may be changed without departing from the scope of the presently disclosed subject matter. Furthermore the foregoing description is for the purpose of illustration only and not for the purpose of limitation.

