# AI_for_Screw_Detection

This project focuses on detecting switches with and without screws using a live camera feed. The model is trained using YOLOv5 to accurately classify and detect screws in various conditions.

## Features

- Real-time detection of switches with and without screws.
- High accuracy and fast processing using YOLOv5.
- Easy-to-use interface for integrating with live camera feeds.
- Detailed logging and visualization of detection results.

## Technologies Used

- Python
- YOLOv5
- OpenCV
- TensorFlow and Keras (for additional model training)
- LabelImg (for labeling the dataset)

## Project setup
-To run this project, you need to install some dependencies:
      -Python 3
      -PyTorch
      -OpenCV
      -Numpy
      -numpy
      -matplotlib
      -PyYAML
-You can install these dependencies using :
pip install -r requirements.txt

## Prepare the Dataset
- structure should look like this:
dataset/
├── train/
├── val/
└── test/


## Install LabelImg for Labeling Images 
*Download  Python  PyQt5 and install lxml. 
*Open cmd and go to labelImg directory
- pyrcc4 -o libs/resources.py resources.qrc
- For pyqt5, pyrcc5 -o libs/resources.py resources.qrc
- python labelImg.py
- python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]

## install yolov5 
- git clone https://github.com/ultralytics/yolov5  # clone
- cd yolov5
- pip install -r requirements.txt  # install

## Yaml file editing
- open the folder data in yolov5\data and open custom_dataset.yaml in notpad.
- change the value of nc to the no of classes present in our dataset
- replace the classnames with our class names
- save the file

## Start Training
- python train.py --data data.yaml --cfg yolov5s.yaml --batch-size 8 --name Model --epochs 50

## Export Trained Model 
- python export.py --weights runs/train/Model/weights/best.pt --include onnx --simplify --opset 12 

## Run Inference (Detection)
- python detect.py --source data/images/ --weights runs/train/exp/weights/best.pt




