# Ieee-Task-ML
Video Classification using CNN Feature Extraction
Problem Statement

The objective of this project is to classify short video clips as real or fake using machine learning techniques. The dataset consists of short MP4 videos organized into class-wise folders.

Dataset

Training videos: 280 (140 real, 140 fake)

Test videos: 100

Video duration: approximately 5–8 seconds

Labels are inferred from folder names (real, fake)

Methodology
Video Feature Extraction

Raw videos cannot be directly used by machine learning models. Each video was processed by sampling evenly spaced frames. A pretrained MobileNetV2 convolutional neural network (trained on ImageNet) was used as a fixed feature extractor. Each frame was converted into a 1280-dimensional embedding.
