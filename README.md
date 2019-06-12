
# Overview of source files

- Main entry
    - ObjectTrack.py: 
         - Use the detection results provided from sagemaker.
         - Use the deep_sort to track the multiple objects.
         - Save video of visualized images with rectangles and track_ids.

- In package deep_sort is the main tracking code:

    - detection.py: Detection base class.
    - kalman_filter.py: A Kalman filter implementation and concrete parametrization for image space filtering.
    - linear_assignment.py: This module contains code for min cost matching and the matching cascade.
    - iou_matching.py: This module contains the IOU matching metric.
    - nn_matching.py: A module for a nearest neighbor matching metric.
    - track.py: The track class contains single-target track data such as Kalman state, number of hits, misses, hit streak, associated feature vectors, etc.
    - tracker.py: This is the multi-target tracker class.
    
- Generating detections
    - generate_detections.py: Generate features for object re-identification, suitable to compare the visual appearance of object bounding boxes using cosine similarity.
    
- Model
    - mars-small128.pb: Trained based on tensorflow-1.4.0. 
       
# Reference

1. https://github.com/Qidian213/deep_sort_yolov3
2. https://github.com/nwojke/deep_sort