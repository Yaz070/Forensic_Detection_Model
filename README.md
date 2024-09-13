# Forensic_Detection_Model

This project implements a YOLO (You Only Look Once) model to detect evidence from digital media 🔍, focusing on forensic analysis 🕵️‍♂️ and crime scene investigation 🚔. The model is trained to detect key types of physical evidence Blood, Handguns, Illegal Substances, Rifles, and Knives (🩸🔫💊🔪) that could be found in media, aiding investigators in identifying critical elements in real-time ⚡. The main goal of the model was to speed up the process of detection along with achieve high accuracy.

# Data Stage:
Our data has approximately 28,000 images

# Training Stage:
Before starting the training process, we conducted thorough research to determine the best optimizer for the model. After evaluating several options, we concluded that Stochastic Gradient Descent (SGD) was the optimal choice for this task due to its performance in achieving better generalization and stability during training.

first we started training the model (YOLOv8l) with 100 epochs using [Dataset_V1](Forensic_Detection_Model/tree/main/Dataset/Dataset_V1) and the results were not satisfied with the intention goal.

second we decided to retrain the model on a new dataset focusing on enhancing it 


confusion matrix
![results](https://github.com/user-attachments/assets/be75e974-6e9a-4754-95d0-d0b355fb3d2e)
![results-2](https://github.com/user-attachments/assets/de32bc89-d46f-4dd0-b8ea-dc12cedf6f64)
