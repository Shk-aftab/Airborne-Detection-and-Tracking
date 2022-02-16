# Airborne Detection and Tracking

## Overview
The Airborne Object Tracking (AOT) dataset is a collection of flight sequences collected onboard aerial vehicles with high-resolution cameras. To generate those sequences, two aircraft are equipped with sensors and fly _planned_ encounters.

The trajectories are designed to create a wide distribution of distances, closing velocities, and approach angles. 

In addition to the so-called planned aircraft, AOT also contains other unplanned airborne objects, which may be present in the sequences.
Those objects are also labeled but their distance information is not available.

Airborne objects usually appear quite small at the distances which are relevant for early detection: 0.01% of the image size on average, down to a few pixels in area (compared to common object detection datasets, which exhibit objects covering more considerable portion of the image). This makes AOT a new and challenging dataset for the detection and tracking of potential aerial collision threats. 

## Dataset

The complete training dataset size is ~>11TB. You can access the dataset in public S3 bucket hosted at `s3://airborne-obj-detection-challenge-training/` by the authors.

## Preprocessing

I downloaded partial dataset (85GB) which includes all the frames with valid encounter of planned airborne object at a distance of 500m from camera. Remove classes other than ['Airplane', 'Helicopter'] and changed it to a single class dataset as `Airborne` 

In total I collected 46314 Images each with a resolution of 2448 X 2048.

## Detection

## Yolov5 - 0.995 mAP @0.5


<p align="center">
  <img src="https://github.com/Shk-aftab/Airborne-Detection-and-Tracking/blob/main/assets/detection/test1.gif" width="640"/>
  <br>
  <img src="https://github.com/Shk-aftab/Airborne-Detection-and-Tracking/blob/main/assets/detection/test2.gif" width="640"/>
  <br>
  <img src="https://github.com/Shk-aftab/Airborne-Detection-and-Tracking/blob/main/assets/detection/bandra.gif" alt="animated" width="640" />
  <br>
  
  <em>Locally captured an aeroplane taking off</em>
</p>

## Tracking

### Yolov5 + DeepSORT

<img src="https://github.com/Shk-aftab/Airborne-Detection-and-Tracking/blob/main/assets/ds_tracking_test1.gif" width="495"/> <img src="https://github.com/Shk-aftab/Airborne-Detection-and-Tracking/blob/main/assets/ds_tracking_test2.gif" width="495"/>




