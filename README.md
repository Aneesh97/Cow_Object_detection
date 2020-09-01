# Introduction

This is a PyTorch implementation of YOLOv3 object detection model based on this: https://github.com/ultralytics/yolov3 implementation by Ultralytics LLC.


# Requirements

Python 3.7 or later with all `pip install -U -r requirements.txt` packages including `torch >= 1.5`.



# Training

If the user wants to train another model this is possible but access to a GPU is required as the code utilises CUDA which has GPU requirements. Running the command python train.py within any of the directories will train a new model from scratch using the training data already placed in the directory. If the user wanted to train a model from a starting point using transfer learning they would execute python train.py --weights [path/to/weights].



# Detections

To perform detections using any of the three networks, the machine must first have the correct environment settings installed. The user should execute pip install -r requirements.txt within the Project directory. Then they navigate to the folder corresponding to the network they wish to use. Running the command python detect.py will execute detections on the validation set for that network. However, if the user wanted to run detections on a custom image that they add then they run python detect.py --source [path/to/image]. This command can also be run with the source flag pointing to a folder with multiple images instead of a singular image. As long as the added image has the correct number of channels for the corresponding network then detections will run and be outputted to the output folder.

Having access to a GPU for detections would be preferable but the time for each detection is still manageable with a CPU; being around 1 second per image with a CPU and 0.029 seconds with a GPU.

# Testing

To test any of the three already trained networks the user must enter the respective directory and run python test.py and this will test the object detection network against the validation set within the directory. Within the terminal there will be results printed for the precision, recall, F1 score and mAP for the network. Like with training the machine must have GPU access for this to run.
