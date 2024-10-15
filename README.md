# MAHYA-FacialRecognitionSystem

This repository contains code and resources for the MAHYA Facial Recognition System, a project designed to build and train a facial recognition model using siamese algorithm, and Inception ResNet V1 for the Encoder. The project consists of different components, including model training and a web-based interface built with Flask.

## Structure

The main files and folders in this repository are as follows:

- `FaceRecognition-Flask.ipynb`: This notebook implements the facial recognition system using Flutter. It includes code for detecting and identifying faces using trained models.

- `EncoderModel.ipynb`: This notebook focuses on training the encoder model using the triplet loss function. The encoder extracts features from the face images, which are used for recognition tasks.

- `Models/`: This folder contains pre-trained model weights and other related files for facial recognition.
  - `enc_model_weights.h5`: The encoder model's weight file used for feature extraction.

## Requirements

The following libraries and frameworks are required to run the notebooks and models in this project:

- Python 3.6 or later
- TensorFlow
- Keras
- OpenCV
- Flask
- Flutter (for the frontend)


## Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Shahadbal/MAHYA-FacialRecognitionSystem.git
   cd MAHYA-FacialRecognitionSystem
   
2. **Install the required dependencies**: Make sure you have a Python virtual environment set up and activate it:
   ```bash
   pip install -r requirements.txt
4. **Running the notebooks**: Open the Jupyter notebooks and run the code cells to execute the training and recognition tasks.

## Using Git Large File Storage (LFS)

This repository uses Git LFS to manage large files. If you're working with model files or other large datasets, make sure to install Git LFS on your system:
```bash
git lfs install
git lfs track "*.h5"


## Project Workflow
Training the Encoder Model: Use the EncoderModel.ipynb notebook to train the encoder model. This model will extract unique facial features for each individual.

Face Recognition: The FaceRecognition-Flask.ipynb notebook implements the face recognition logic using the pre-trained encoder model.

Web Application: The Flask-based web application enables users to interact with the face recognition system via a user-friendly interface.
