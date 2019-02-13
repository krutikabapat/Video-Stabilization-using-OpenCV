# Video-Stabilization

Video Stabilization Using Point Feature Matching in OpenCV.  

This mainly involves reducing the effect of motion due to translation or rotation or any movement in camera.
In this, Euclidean Motion Model is used instead of Affine or Homographic transformation, because it is adequate for motion stabilization.  

## Steps for video stabilization

1. Capture two consequent frames of a video.  
2. Find motion between those two frames.  
3. Correct the motion.

## Finding motions between frames

1. Find good features in the current frame and previous frame (`goodGeaturesToTrack`) and (`calcOpticalFlowPyrLK`).  
2. We use two set of points to find rigid transform that maps previous frame to the current frame(`estimateRigidTranform`).  
3. Once the motion is estimated, we store the rotated, translated values.  
4. We soothe the values, found in step 3 (moving average filter).  
5. Calculate smooth motion between frames (trajectory).  
6. Apply smoothed camera motion to frames.  

## Important functions used:-

1. `calcOpticalFlowPyrLK()`  
   a) `nextPts` - output vector of 2D points (with single-precision floating-point coordinates) containing the calculated new         positions of input features in the second image.  
   b) `status` – output status vector (of unsigned chars); each element of the vector is set to 1 if the flow for the                 corresponding features has been found, otherwise, it is set to 0.  
   c) `err` -  outputs vector of errors, if the flow wasn’t found then the error is not defined.  
  
2. `estimateRigidTransform()`  
   a) Computes an optimal affine transformation between two 2D point sets.  
   
 ## Version Requirements
 
 1. Python 2.7 or Python 3.x
 2. OpenCV version 3.x.x
   
## Usage

`python video_stabilization.py`


  





