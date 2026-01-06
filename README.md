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

Temporal Feature Aggregation

To represent an entire video while preserving temporal information:

The mean of frame-level embeddings was computed to capture average visual appearance.

The standard deviation of embeddings was computed to capture frame-to-frame variability.

These two vectors were concatenated to form a 2560-dimensional feature representation for each video.

Models Evaluated

Logistic Regression (baseline)

Random Forest

Neural Network (Multilayer Perceptron)

Baseline models performed close to random, indicating that the extracted features required a more flexible non-linear classifier.

Final Model

A shallow neural network was trained on the extracted features after feature scaling. During evaluation, predicted probabilities were inverted to align with the target label definition. The final model demonstrated meaningful class separation with a validation ROC-AUC of approximately 0.66 after correction.

Output

Predictions were generated for the test dataset and saved as submission.csv.

Output Format

Video_Name: Name of the video file

Prediction: Predicted class label (0 or 1)

Probability: Confidence score between 0 and 1

Tools and Libraries

Python

OpenCV

TensorFlow / Keras

scikit-learn

NumPy, Pandas

Google Colab

Conclusion

This project demonstrates an effective approach for video classification by combining CNN-based feature extraction, temporal aggregation, and a neural network classifier. The methodology is suitable for small video datasets where training end-to-end video models is impractical.
