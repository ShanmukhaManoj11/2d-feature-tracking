# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

This project implements different keypoint detectors and descriptor extractors, compares them to suggest appropriate detector-descriptor pair to be able to estimate relative motion of the lead vehicle (in-turn time to collision for collision avoidance) in image sequences. 

List of keypoint detectors - SHITOMASI, HARRIS, FAST, BRISK, ORB, AKAZE, SIFT

List of descriptor extractors - BRISK, BRIEF, ORB, FREAK, AKAZE, SIFT

Metric 1: Average number of keypoints detected

|           | total # keypoints | # keypoints in ROI | 
|-----------|-------------------|--------------------|
| SHITOMASI |        1342       |        118         |
|-----------|-------------------|--------------------|
| HARRIS    |         174       |         25         |
|-----------|-------------------|--------------------|
| FAST      |        4921       |        410         |
|-----------|-------------------|--------------------|
| BRISK     |        2712       |        276         |
|-----------|-------------------|--------------------|
| ORB       |         500       |        116         |
|-----------|-------------------|--------------------|
| AKAZE     |        1343       |        167         |
|-----------|-------------------|--------------------|
| SIFT      |        1386       |        139         |