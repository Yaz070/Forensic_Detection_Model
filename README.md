# Forensic Detection Model

This project implements a YOLO (You Only Look Once) model to detect evidence from digital media 🔍, focusing on forensic analysis 🕵️‍♂️ and crime scene investigation 🚔. The model is trained to detect key types of physical evidence Blood, Handguns, Illegal Substances, Rifles, and Knives (🩸🔫💊🔪) that could be found in media, aiding investigators in identifying critical elements in real-time ⚡. The main goal of the model was to speed up the process of detection along with achieve high accuracy.

## Dataset Stage 🗂️:
We ensured that our dataset consisted of high quality and diverse images to train the model effectively. The images were collected to meet the necessary standards for clarity and variation, ensuring that the model could generalize well across different environments and scenarios.

To streamline the preparation process, we used Roboflow for image labeling, augmentation, and dataset splitting. This platform enabled us to efficiently label the images and split them into training, validation, and testing sets. In total, approximately 28,000 images were used across the different versions of the dataset.

## Training Stage
Before starting the training process, we conducted a thorough analysis to determine the best optimizer for our model. After evaluating several options, we concluded that Stochastic Gradient Descent (SGD) was the most suitable choice, offering improved generalization and stability.

1️⃣ Initial Training:

The first stage of training involved the YOLOv8l model trained on [Dataset_V1](Dataset/Dataset_V1), which consisted of approximately 27,721 images over the course of 100 epochs. While the model showed promising improvements in performance metrics, the results did not fully meet our expected goals, particularly in detecting certain evidence classes.

2️⃣ Retraining:

To enhance accuracy in specific classes, we retrained the model using a refined dataset, [Dataset_V2](Dataset/Dataset_V2), which contained 421 images. The retraining was conducted over a reduced period of 15 epochs to fine-tune the model's performance. This smaller, focused dataset allowed us to target and improve the detection of critical evidence classes. We also incorporated early stopping to prevent overfitting and employed data augmentation techniques to improve the model’s robustness.

## confusion matrix
![results](https://github.com/user-attachments/assets/be75e974-6e9a-4754-95d0-d0b355fb3d2e)
![results-2](https://github.com/user-attachments/assets/de32bc89-d46f-4dd0-b8ea-dc12cedf6f64)

🔸 Training Loss: Both box loss and class loss decreased significantly during training in both datasets, indicating improved model performance. However, the retraining on Dataset_V2 (15 epochs) showed faster convergence compared to the larger Dataset_V1 (100 epochs), especially in classifying objects.

🔸 Validation Loss: Similarly, the validation loss dropped more rapidly with Dataset_V2, reflecting better generalization and model performance on unseen data. The model became more accurate in predicting both object locations (box loss) and classifications (class loss) within fewer epochs.

🔸 Key Insight: The smaller Dataset_V2 led to faster convergence and more efficient learning, improving the detection accuracy for certain classes in a shorter time.
