# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

This project implements different keypoint detectors and descriptor extractors, compares them to suggest appropriate detector-descriptor pair to be able to estimate relative motion of the lead vehicle (in-turn time to collision for collision avoidance) in image sequences. 

List of keypoint detectors - SHITOMASI, HARRIS, FAST, BRISK, ORB, AKAZE, SIFT

List of descriptor extractors - BRISK, BRIEF, ORB, FREAK, AKAZE, SIFT

For every possible detector-descriptor pair from the above lists, following metrics are computed to identify a good pair balancing accuracy and execution time,

#### Metric 1: Average number of keypoints detected

| Detector  | total # keypoints | # keypoints in ROI | 
|-----------|-------------------|--------------------|
| SHITOMASI |        1342       |        118         |
| HARRIS    |         174       |         25         |
| FAST      |        4921       |        410         |
| BRISK     |        2712       |        276         |
| ORB       |         500       |        116         |
| AKAZE     |        1343       |        167         |
| SIFT      |        1386       |        139         |

#### Metric 2a : Average execution time for detector

| Detector  | exec time (ms) | 
|-----------|----------------|
| SHITOMASI |      21.25     |
| HARRIS    |      23.45     |
| FAST      |       4.35     |
| BRISK     |     277.56     |
| ORB       |      14.04     |
| AKAZE     |      82.14     |
| SIFT      |     113.59     |

#### Metric 2b : Average execution time for descriptor with corresponding detector

| Det\Desc  | BRISK | BRIEF | ORB  | FREAK | AKAZE | SIFT  | 
|-----------|-------|-------|------|-------|-------|-------|
| SHITOMASI | 1.45  | 1.04  | 1.25 | 37.34 | N/A   | 19.79 |
| HARRIS    | 0.52  | 0.59  | 1.01 | 36.99 | N/A   | 19.58 |
| FAST      | 4.16  | 2.69  | 2.53 | 45.29 | N/A   | 42.11 |
| BRISK     | 2.85  | 1.00  | 4.53 | 40.01 | N/A   | 44.69 |
| ORB       | 1.37  | 0.97  | 6.30 | 38.93 | N/A   | 51.65 |
| AKAZE     | 2.10  | 0.84  | 2.72 | 40.76 | 67.41 | 26.60 |
| SIFT      | 1.54  | 0.63  | N/A  | 38.53 | N/A   | 90.32 |

#### Metric 3: Average number of matched points for detector-descriptor pairs

| Det\Desc  | BRISK | BRIEF | ORB | FREAK | AKAZE | SIFT | 
|-----------|-------|-------|-----|-------|-------|------|
| SHITOMASI | 85    | 105   | 101 | 85    | N/A   | 103  |
| HARRIS    | 16    | 20    | 18  | 16    | N/A   | 18   |
| FAST      | 243   | 315   | 308 | 248   | N/A   | 310  |
| BRISK     | 175   | 190   | 169 | 170   | N/A   | 183  |
| ORB       | 84    | 61    | 85  | 47    | N/A   | 85   |
| AKAZE     | 135   | 141   | 132 | 132   | 140   | 141  |
| SIFT      | 66    | 78    | N/A | 66    | N/A   | 89   |

From above metric information, FAST detector produces maximum number of keypoints per image with least execution time among other descriptors. FAST-BRIEF pair produces the highest number of matches.

Considering the number of matching keypoints extracted and run-time, following detector-descriptor pairs are recommended 
1. FAST - BRIEF
2. FAST - ORB
3. FAST - BRISK