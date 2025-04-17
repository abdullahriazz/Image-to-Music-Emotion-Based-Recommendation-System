# Image-to-Music-Emotion-Based-Recommendation-System
Overview
This project develops an automated system that recommends music tracks based on the emotional tone of input images. By leveraging machine learning, the system analyzes visual and audio content to extract mood-related features, maps them to a shared emotional space, and suggests songs that align with the image's emotional profile. The goal is to streamline the process of pairing visuals with music, enhancing user experience in platforms like Snapchat or Instagram.

Motivation
Selecting the perfect song to match the vibe of an image is often time-consuming. This project automates the process by using advanced machine learning techniques to analyze emotional cues in images and audio, enabling seamless and emotionally resonant music recommendations.

Features
Emotion Analysis: Extracts emotional features from images using the Emotion6 dataset and from audio using the DEAM dataset.
Machine Learning Models:
Vision Transformer (ViT) for image emotion classification.
Dense neural networks for audio valence-arousal prediction and emotion classification.
Data Preprocessing:
Audio: Spectral analysis, feature extraction (e.g., mel-spectrograms, spectral centroid), and dimensionality reduction.
Image: Resolution standardization, color normalization, and data augmentation.
Emotional Mapping: Aligns image and audio emotions in a shared space for accurate song recommendations.
Datasets
DEAM (Dynamic Emotional Analysis of Music):
1,802 songs with valence and arousal annotations (1-9 scale, updated every 0.5s).
Used for audio emotion recognition, focusing on emotional dynamics.
Emotion6:
1,980 images labeled with six basic emotions (anger, disgust, fear, joy, sadness, surprise).
Balanced dataset designed for affective computing.
Methodology
Data Preprocessing:
Audio: Extracted 1,387 features using librosa, normalized valence/arousal to [-1, 1], and applied dimensionality reduction (e.g., PCA, LASSO).
Image: Standardized to 224x224 pixels, applied augmentation (rotation, flips), and converted to TensorFlow tensors.
Model Implementation:
Audio Models: Three neural networks (Unprocessed, Correlation Threshold, RFE with Random Forest) predict valence-arousal, followed by a classifier for six emotions.
Image Model: Fine-tuned Vision Transformer (ViT-base-patch16-224) for direct emotion classification.
Evaluation:
Audio models assessed using Mean Absolute Error (MAE) for valence-arousal and accuracy for emotion classification.
Image model evaluated for emotion classification accuracy.
Recommendation: Maps image emotions to song emotions, recommending tracks with matching profiles.
Results
Audio Model Performance:
RFE (Random Forest) achieved the lowest MAE (0.1114) for valence-arousal prediction.
Correlation Threshold model achieved the highest emotion classification accuracy (0.9971).
Example Prediction:
For an image of Superman, the system recommended joyful tracks (e.g., "Pal Pal", "Trance") with high valence and arousal.
