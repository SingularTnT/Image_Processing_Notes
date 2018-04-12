# Using the Kinect® for Windows® V1 in Matlab

This document shows how to obtain the data available from Kinect for Windows V1 sensor using Image Acquisition Toolbox.

## Kinect for Windows Sensor Components and Specifications

<div align="center">
  <p>kinect version 1 senser</p>
  <img src="img/kinect v1.jpg" width="700px" />
</div>

Inside the sensor case, a Kinect for Windows sensor contains:
- An RGB camera that stores three channel data in a 640x480 resolution. This makes capturing a color image possible.
- An infrared (IR) emitter and an IR depth sensor. The emitter emits infrared light beams and the depth sensor reads the IR beams reflected back to the sensor. The reflected beams are converted into depth information measuring the distance between an object and the sensor. This makes capturing a depth image possible.
- A multi-array microphone, which contains four microphones for capturing sound. Because there are four microphones, it is possible to record audio as well as find the location of the sound source and the direction of the audio wave.
- A 3-axis accelerometer configured for a 2G range, where G is the acceleration due to gravity. It is possible to use the accelerometer to determine the current orientation of the Kinect.

<div align="center">
  <p>kinect version 1 senser components</p>
  <img src="img/kinect v1 components.png" width="700px" />
</div>

#### Specifications for the Kinect

|Kinect | Array Specifications|
| :------------ |:---------------:|
|Color Camera  | 640 x 480 |
|Depth Camera  | 320 x 240 |
|Max Depth Distance  | ~4.5 M |
|Min Depth Distance  | 40 cm in near mode |
|Horizontal Field of View  | 57 degrees |
|Vertical Field of View  | 43 degrees |
|Vertical tilt range  | 	±27° |
|Frame rate (depth and color stream) | 30 frames per second (FPS) |
|Audio format| 16-kHz, 24-bit mono pulse code modulation (PCM) |
|Audio input characteristics | A four-microphone array with 24-bit analog-to-digital converter (ADC) and Kinect-resident signal processing including acoustic echo cancellation and noise suppression |
|Accelerometer characteristics | A 2G/4G/8G accelerometer configured for the 2G range, with a 1° accuracy upper limit |
|Tilt Motor  | yes |
|Skeleton Joints Defined  | 20 joints |
|Full Skeletons Tracked  | 2 |
|USB Standard  | 2.0 |
|Supported OS  | Win 7, Win 8, Win10 |

Note: The resolution of the depth stream is dependent on the frame rate, and is specified by the DepthImageFormat Enumeration enumeration. Similarly, the resolution of the color stream is specified by the ColorImageFormat Enumeration enumeration.

## Dependece

- [Matlab](https://www.mathworks.com/) -- R2013a and later
- [Kinect for Windows SDK 1.6](https://www.microsoft.com/en-us/download/details.aspx?id=34808)
- [Image Acquisition Toolbox](https://ww2.mathworks.cn/products/imaq.html)
- [Computer Vision System Toobox](https://ww2.mathworks.cn/products/computer-vision.html) -- (optional)
- [OpenNI](http://www.openni.ru/) -- (optional)

## Quick Start: Using the Kinect® for Windows® V1 from Image Acquisition Toolbox™

# Detectron

Detectron is Facebook AI Research's software system that implements state-of-the-art object detection algorithms, including [Mask R-CNN](https://arxiv.org/abs/1703.06870). It is written in Python and powered by the [Caffe2](https://github.com/caffe2/caffe2) deep learning framework.

At FAIR, Detectron has enabled numerous research projects, including: [Feature Pyramid Networks for Object Detection](https://arxiv.org/abs/1612.03144), [Mask R-CNN](https://arxiv.org/abs/1703.06870), [Detecting and Recognizing Human-Object Interactions](https://arxiv.org/abs/1704.07333), [Focal Loss for Dense Object Detection](https://arxiv.org/abs/1708.02002), [Non-local Neural Networks](https://arxiv.org/abs/1711.07971), [Learning to Segment Every Thing](https://arxiv.org/abs/1711.10370), [Data Distillation: Towards Omni-Supervised Learning](https://arxiv.org/abs/1712.04440), and [DensePose: Dense Human Pose Estimation In The Wild](https://arxiv.org/abs/1802.00434).

<div align="center">
  <img src="demo/output/33823288584_1d21cf0a26_k_example_output.jpg" width="700px" />
  <p>Example Mask R-CNN output.</p>
</div>

## Introduction
