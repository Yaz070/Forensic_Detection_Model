# Forensic Detection Model

This project implements a YOLO (You Only Look Once) model to detect evidence from digital media 🔍, focusing on forensic analysis 🕵️‍♂️ and crime scene investigation 🚔. The model is trained to detect key types of physical evidence Blood, Handguns, Illegal Substances, Rifles, and Knives (🩸🔫💊🔪) that could be found in media, aiding investigators in identifying critical elements in real-time ⚡. The main goal of the model was to speed up the process of detection along with achieve high accuracy.

## Dataset Stage 🗂️:
We ensured that our dataset consisted of high quality and diverse images to train the model effectively. The images were collected to meet the necessary standards for clarity and variation, ensuring that the model could generalize well across different environments and scenarios.

To streamline the preparation process, we used Roboflow for image labeling, augmentation, and dataset splitting. This platform enabled us to efficiently label the images and split them into training, validation, and testing sets. In total, approximately 28,000 images were used across the different versions of the dataset.

## Training Stage:
Before initiating the training process, we conducted thorough research to identify the most suitable optimizer for our model. After evaluating several options, we determined that Stochastic Gradient Descent (SGD) was the best choice, as it provided improved generalization and stability throughout training.

First, we trained the YOLOv8l model for 100 epochs using the initial dataset, [Dataset_V1](Forensic_Detection_Model/tree/main/Dataset/Dataset_V1). However, the results did not fully meet our desired objectives in terms of prediction accuracy.

To improve performance, we decided to retrain the model using an updated dataset, [Dataset_V2](Forensic_Detection_Model/tree/main/Dataset/Dataset_V2), with a reduced training duration of 15 epochs. The retraining focused on enhancing the accuracy of specific classes to achieve the desired results. We also applied early stopping to avoid overfitting and incorporated data augmentation to boost the model’s robustness.

confusion matrix
![results](https://github.com/user-attachments/assets/be75e974-6e9a-4754-95d0-d0b355fb3d2e)
![results-2](https://github.com/user-attachments/assets/de32bc89-d46f-4dd0-b8ea-dc12cedf6f64)
