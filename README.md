# Video-Stabilization
Video Stabilization Using Point Feature Matching in OpenCV.  

This mainly involves reducing the effect of motion due to translation, or rotation or any movement in camera.
In this, Euclidien Motion Model is used instead of Affine or Homographic transformation, because it is adequate for motion stabilization.  


## Steps for video stabilization:-

1. Capture two frames of a video.  
2. Find motion between thos two frames.  
3. Correct the motion.  


## Finding motins between frames:-

1. Find good features in the current frame and previous frame.    
2. We use two set of points to find rigid transform that maps previous frame to the current frame(estimateRigidTranform).  
3. Once the motion is estimated, we store the rotated, translated values.  
4. We soothe the values, found in step 3.  
5. Calculate smooth motion between frames. 
6. Apply smoothed camera motion to frames.  





