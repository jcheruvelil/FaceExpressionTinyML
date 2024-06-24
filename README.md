# FaceExpressionTinyML
Joshua Cheruvelil Senior Project 2024

Follow the instructions in the following CoLab:
https://colab.research.google.com/drive/1uGkObpi2yn1mogUFRF15ckiPz0NBx_sg#offline=true&sandboxMode=true


Hardware Needed:
- Arduino Nano 33 BLE Sense
- 0V7675 Camera
(Both contained in the TinyML kit)

# Directions (details in CoLab)

## 1. Prepare Dataset
We will be using the Facial Expression Recognition dataset (FER) from Kaggle. This dataset contains images for 7 expression categories, but we will only be focusing on 2 expressions - happy and sad.

- Download the dataset from https://www.kaggle.com/datasets/msambare/fer2013
- Upload the downloaded zipfile to the CoLab using the Files side menu to the left
- Run the code cell to unzip the file and extract the happy and sad classes from the dataset. Be sure to define your uploaded file path.

## 2. Transfer Learning Approach
The CoLab will first walk through a transfer learning approach that uses a pretrained model (MobileNetV3) with modifications.

## 3. Simpler Model From Scratch
The second apporach that the CoLab will walk through is building your own model which will allow for more customization and optimization for a microcontroller.

## 4. Convert to TensorFlow Lite Model
The next crucial step in the process is optimizing your trained model for use on a microcontroller which involves conversion to TF Lite. 

## 5. Deploying to your Board
The last step in the process is deploying your model to your microcontroller. 

To Deploy:

- Make sure you have the Arduino IDE installed and then navigate to https://github.com/jcheruvelil/FaceExpressionTinyML/tree/main/expression_detection and download the Arduino sketch.
- Download fer_model.cc generated from the CoLab.
- In expression_detect_model_data.cpp copy and paste just the byte array from fer_model.cc into the byte array field, and set g_expression_detect_model_data_len to the number of bytes listed at the bottom of the fer_model.cc file.
- Make sure your 0V7675 Camera is hooked up to your Nano 33 BLE board and connect the board to your laptop via USB.
- Compile and Upload the Arduino sketch to your board. Compilation will take a long time on your first time compiling.
- Once uploaded, open up the Serial monitor to see the happy and sad scores for each image capture. Make sure the camera is far enough away from your face while capturing images (extend your arm straight while holding the board/camera). A green led corresponds to a happy expression while a red led corresponds to a sad expression. A blue led lights up between every image capture.
- Observe how well or how poorly your model performs. Try different lightings and environments and feel free to experiment by changing things in any of the previous steps to obtain different results.

Have fun!
