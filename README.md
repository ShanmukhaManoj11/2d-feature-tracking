# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

This project implements different keypoint detectors and descriptor extractors, compares them to suggest appropriate detector-descriptor pair to be able to estimate relative motion of the lead vehicle (in-turn time to collision for collision avoidance) in image sequences. 

List of keypoint detectors - SHITOMASI, HARRIS, FAST, BRISK, ORB, AKAZE, SIFT

List of descriptor extractors - BRISK, BRIEF, ORB, FREAK, AKAZE, SIFT

### Metric 1: Average number of keypoints detected

| Detector  | total # keypoints | # keypoints in ROI | 
|-----------|-------------------|--------------------|
| SHITOMASI |        1342       |        118         |
| HARRIS    |         174       |         25         |
| FAST      |        4921       |        410         |
| BRISK     |        2712       |        276         |
| ORB       |         500       |        116         |
| AKAZE     |        1343       |        167         |
| SIFT      |        1386       |        139         |

### Metric 2a : Average execution time for detector

| Detector  | exec time (ms) | 
|-----------|----------------|
| SHITOMASI |      20.35     |
| HARRIS    |      25.18     |
| FAST      |       4.75     |
| BRISK     |     284.13     |
| ORB       |      14.63     |
| AKAZE     |      87.40     |
| SIFT      |     118.87     |

### Metric 2b : Average execution time for descriptor

| Descriptor  | exec time (ms) | 
|-------------|----------------|
| BRISK       |     242.49     |
| BRIEF       |       1.29     |
| ORB         |       3.01     |
| FREAK       |      40.43     |
| AKAZE       |      76.48     |
| SIFT        |      44.59     |

### Metric 3: Average number of matched points for detector-descriptor pairs

|           | BRISK | BRIEF | ORB | FREAK | AKAZE | SIFT | 
|-----------|-------|-------|-----|-------|-------|------|
| SHITOMASI | 85    | 105   | 101 | 85    | N/A   | 103  |
| HARRIS    | 16    | 20    | 18  | 16    | N/A   | 18   |
| FAST      | 243   | 315   | 308 | 248   | N/A   | 310  |
| BRISK     | 175   | 189   | 169 | 170   | N/A   | 183  |
| ORB       | 84    | 61    | 85  | 47    | N/A   | 85   |
| AKAZE     | 135   | 141   | 132 | 132   | 140   | 141  |
| SIFT      | 66    | 78    | N/A | 66    | N/A   | 89   |