# ML_PROJECT

# Face Recognition System README

This code implements a simple face recognition system using Python and OpenCV. It captures images from a webcam, trains a face recognition model, and then uses the trained model to recognize and authenticate users based on their faces.

## Prerequisites

Before running the code, you need to make sure you have the following libraries installed:

- `urllib.request`: For making HTTP requests.
- `cv2` (OpenCV): For computer vision tasks.
- `numpy`: For numerical operations.

You can install these libraries using `pip` if you haven't already:

```bash
pip install opencv-python numpy
```

## Usage

1. **Data Collection**: The code collects facial data from your webcam to create a dataset for training the recognition model. It captures 200 samples of your face.

2. **Model Training**: The captured facial data is used to train the recognition model using the LBPH (Local Binary Pattern Histogram) algorithm.

3. **Face Recognition**: After training, the code uses the trained model to recognize your face in real-time via the webcam. It calculates confidence levels and displays whether you are recognized as an authorized user.

4. **Access Control**: If the recognition confidence is above 80%, it will grant access and send an HTTP request to unlock a resource (e.g., a door lock) using the AWS Lambda endpoint provided in the code.

5. **Access Denied**: If the recognition confidence is below 80% or if no face is detected, access is denied and the system remains locked.


## Customization
- Replace the AWS Lambda endpoints (`https://6qct366eze.execute-api.ap-south-1.amazonaws.com/test/unlock`) with your own if you have an access control system.

## Acknowledgments

- The code utilizes the LBPH algorithm provided by OpenCV for face recognition.
- The Haar Cascade classifier for face detection is also provided by OpenCV.
