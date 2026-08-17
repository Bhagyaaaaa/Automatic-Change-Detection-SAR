Automatic Change Detection in SAR Images

A deep learning capstone project that detects surface changes between two SAR (Synthetic Aperture Radar) satellite images of the same area, captured at different times, using a U-Net segmentation model built in TensorFlow/Keras.

Overview

Given a pre-event and post-event SAR image of a location plus a ground-truth change mask, the notebook:

Cleans up and organizes an uploaded image dataset (pre/post/ground-truth triplets grouped by scene name)
Reduces SAR speckle noise with a median filter
Preprocesses each image pair (grayscale, resize, normalize)
Trains a U-Net convolutional network to predict a binary change mask
Evaluates predictions against the ground truth using accuracy, precision, recall, and F1-score

This kind of pipeline is used in real-world applications such as flood mapping, deforestation monitoring, urban expansion tracking, and disaster assessment.

Tech Stack
Python (Google Colab)
TensorFlow / Keras (U-Net architecture)
OpenCV for image preprocessing and speckle filtering
NumPy / Matplotlib
Project Structure
Automatic-Change-Detection-SAR/
├── CAPSTONE_PROJECT.ipynb          # Full pipeline: preprocessing, U-Net, training, evaluation
├── FINALREPORT.pdf                 # Written project report
├── Final Research Paper[capt].pdf  # Research paper write-up
├── FINAL_PHOTOS.pdf                # Result visualizations
└── CAPSTONE_PROJECT_PPT_FINAL.pptx # Presentation deck
How It Works
Data ingestion – pre-event, post-event, and ground-truth mask images are uploaded and grouped by scene name.
Preprocessing – each image is denoised with a median filter to reduce SAR speckle noise, converted to grayscale, resized to 128×128, and normalized.
Model – a compact U-Net encoder/decoder segments the pixel-level change map from the paired inputs.
Evaluation – predicted masks are compared against ground truth per scene, reporting accuracy, precision, recall, and F1-score.
Running the Notebook

This project was built and run in Google Colab (it uses google.colab.files for uploads):

Open CAPSTONE_PROJECT.ipynb in Google Colab
Run the first cell and upload your dataset (pre-event / post-event / ground-truth image triplets, named so each scene shares a common prefix, e.g. scene1_pre.bmp, scene1_post.bmp, scene1_gt.bmp)
Run the remaining cells in order to preprocess, train, and evaluate

To run locally instead, replace the Colab upload cell with a local file path and install:

bash
pip install opencv-python tensorflow numpy matplotlib
Documentation

The full methodology, results, and analysis are written up in FINALREPORT.pdf and Final Research Paper[capt].pdf, with the accompanying CAPSTONE_PROJECT_PPT_FINAL.pptx used for presentation.

Author

Bhagyaaaaa — GitHub
