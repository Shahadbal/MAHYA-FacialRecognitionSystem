# MAHYA-FacialRecognitionSystem

This repository contains code and resources for the MAHYA Facial Recognition System, a project designed to build and train a facial recognition model using siamese algorithm, and Inception ResNet V1 for the Encoder. The project consists of different components, including model training and a web-based interface built with Flask.

## Structure

The main files and folders in this repository are as follows:

1. `FaceRecognition-Flask.ipynb`:
   - **Description**: This notebook serves as the backend for the face recognition system using Flask. It manages incoming requests from the Flutter application and processes them to identify faces.
   - **Key Components**:
   - **Flask Setup**: Initializes the Flask server to handle requests.
   - **Ngrok Integration**: Uses ngrok to expose the local Flask server to the internet, enabling communication with the Flutter frontend.
   - **Face Recognition Logic**: Implements the logic for detecting and recognizing faces based on incoming image data.

2. `EncoderModel.ipynb`:
    - **Description**: This notebook trains the encoder network that generates face encodings. The training uses a triplet loss function to optimize the encodings for better recognition accuracy.
   - **Key Components**:
     - **Face Detection**: Utilizes Multi-task Cascaded Convolutional Networks (MTCNN) for detecting faces during training, ensuring high accuracy.
     - **Encoder Network**: Implements the Inception ResNet v1 architecture to create 128-dimensional face encodings from input images.
     - **Training Process**: Describes how the encoder is trained using triplets, which consist of anchor, positive, and negative face images.
     - **Triplet Loss Calculation**: Triplet loss is utilized during the training of the encoder.
     - **Triplet Mining**: Identifying hard and semi-hard triplets for effective training.

3. `Models/`: 
  - `enc_model_weights.h5`
  - `Inception_ResNet_v1.json`


## Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Shahadbal/MAHYA-FacialRecognitionSystem.git
   cd MAHYA-FacialRecognitionSystem
   
2. **Install the required dependencies**: Make sure you have a Python virtual environment set up and activate it:
   ```bash
   pip install -r requirements.txt
4. **Running the notebooks**: Open the Jupyter notebooks and run the code cells to execute the training and recognition tasks.
5. **Preparation for Running FaceRecognition-Flask.ipynb**:
   - Create a Directory: In the root directory of the project, create a folder called Face_database.
   - Upload Images: Add images of the individuals you wish to recognize into the Face_database folder.


## Using Git Large File Storage (LFS)

This repository uses Git LFS to manage large files. If you're working with model files or other large datasets, make sure to install Git LFS on your system:
    ```bash
    git lfs install
    git lfs track "*.h5"
    

## Project Workflow
- Utilize the EncoderModel.ipynb notebook to train the encoder model. This model is responsible for extracting distinct facial features for each individual, leveraging triplet loss to ensure that faces of the same person are closer in the embedding space compared to those of different individuals.

- The FaceRecognition-Flask.ipynb notebook implements the face recognition functionality using the pre-trained encoder model. It processes input images to generate facial encodings and compares them against stored encodings in the Face_database to identify known individuals based on proximity in the embedding space.
  
- The project utilizes Flask to establish a connection between the face recognition system and a Flutter frontend, using the ngrok API for secure tunneling. This setup allows users to interact with the face recognition system through a user-friendly Flutter interface. Users can upload images, initiate recognition processes, and receive immediate feedback on identified individuals, enabling seamless interaction with the underlying face recognition technology.
