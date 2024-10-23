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

# Object Recognition Flow
1. Image is available from the detection flow.
2. Run algorithms to recognise broad category of objects including
   - Fishing vessel
   - Trawler
   - Merchant Vessel
   - Buoy
   - Man overboard
   - Lighthouse
   - Navigation Marks
   - Warship
   - Boat
   - Yatch
   - Oil rig
   - Dredger
   - Tug
4. Attach information to object ID
5. Send information to be displayed.
6. Send recognition information to identification algorithm, hull form recogniser, and OCR algorithms.

# Identification Algorithm
1. If object recognised are either Merchant Vessel or Warships, this algorithm will further classify them into the respective types and classes.
2. If merchant vessel, direct images to MV type identification algorithms.
3. If warships, direct images to Warship class identification algorithms.
4. Append identification annotation to identity and recognition information on the display.
5. Store identification information.
6. Pass images of day for MV and Warships to OCR algorithm.

# Hull form detection
1. Obtain EO clear of fishing vessel from recognition algorithm.
2. Obtain hull form bounding boxes for fishing vessels.
3. Send hull form of fishing vessels to colour recognition and OCR algorithms.

# Colour recognition algorithm
1. This algorithm is only for fishing vessels.
2. Obtain images from hull form algorithm.
3. Determine major colour of the hull.
4. Pass information of ID, hull colour to recognise region of fishing vessel.

# OCR Algorithm
1. Obtain images from identification and hull form algorithms.
2. Recognise alphanumeric characters
3. Record this information along with relevant ID of the object into database.
4. Display OCR information.
