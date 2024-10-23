![image](https://github.com/user-attachments/assets/5f35bfe7-2c4d-4e2e-95b5-2f1e308a8f69)
# Image Manupilations
1. Image seggregation and integration as single EO and single IR image.
2. Image stitching - to obtain single image over the entire horizon.
3. Image enhancement - to improve chances of Detection, Recognition, Identification, and Tracking of objects

# Object Detection Flow
1. Image is available as a single image from all EO cameras and a single image from all IR cameras.
2. Run an algorithm on each image stream to confirm detection of objects of interest.
3. Send information for display on video from camera system.
4. Record the object information including
  - Object ID number
  - Object bearing
    - Obtain frame reference wrt the True North or Ship's Head.
    - If from Ship's Head, obtain ship's heading.
    - Calculate bearing based on X value of image centre and frame reference.
  - LRF range information on the specified bearing.
5. Send detected information to recognition and identification algorithms.
