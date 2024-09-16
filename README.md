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

🔸 Training Loss: Both box loss and class loss decreased significantly during training. After fine-tuning the model with Dataset_V2 (15 epochs), the losses showed even faster convergence compared to the initial training on Dataset_V1 (100 epochs). This demonstrates that the model became more efficient at classifying objects after fine-tuning.

🔸 Validation Loss: Validation loss also dropped more rapidly after fine-tuning with Dataset_V2, indicating improved generalization on unseen data. The fine-tuned model became more accurate in predicting both object locations (box loss) and classifications (class loss) within fewer epochs, thanks to the focused adjustment on specific classes.

🔸 Key Insight: Fine-tuning with Dataset_V2 helped the model achieve faster convergence and better detection accuracy for certain classes. This refinement allowed the model to perform more efficiently.

## Model Predictions on Real Images 🎯

After training and fine-tuning the model, we tested it on real-world forensic images to evaluate its performance in detecting evidence in real scenarios. Below are some examples showcasing the model's predictions:

<div style="display: flex; gap: 20px; justify-content: flex-start;">
  <div align="center">
    <h3>1️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/e91bd8be-0e8a-4b79-869f-74e902f616f9" alt="Blood" width="600"/>
    <p>Prediction: Blood detected 🩸</p>
  </div>
  <div align="center">
    <h3>2️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/7a5e607a-c4c9-4040-89eb-1d1e7c6513d3" alt="Illegal Substances detected" width="600"/>
    <p>Prediction: Illegal Substances detected 💊</p>
  </div>
    <div align="center">
    <h3>3️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/1a42068e-5f52-445b-95d8-e805e4be75e5" alt="Illegal Substances detected" width="600"/>
    <p>Prediction: Rifle 🪖</p>
  </div>
  </div>
    <div align="center">
    <h3>4️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/5f1cbf2d-0b31-448b-adfa-02f448941bab" alt="Illegal Substances detected" width="600"/>
    <p>Prediction: Handgun 🔫</p>
  </div>
  </div>
    <div align="center">
    <h3>5️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/ca556b43-d1a7-4022-b1f7-99e0c156438c" alt="Illegal Substances detected" width="600"/>
    <p>Prediction: Knife 🔪</p>
  </div>
  </div>
    <div align="center">
    <h3>6️⃣ Test Image</h3>
    <img src="https://github.com/user-attachments/assets/db1b9388-86c8-4027-9e2d-798a414de2c4" alt="Illegal Substances detected" width="600"/>
    <p>Prediction: Multiple Predictions 🔫🔪</p>
  </div>
  </div>
    <div align="center">
    <h3>Test Video</h3>
    <img src="https://github.com/user-attachments/assets/5ce29950-7b98-4f87-8cb4-fdcbcd4af888" alt="Illegal Substances detected"/>
    <p>Prediction: Handgun 🔫</p>
  </div>
</div>






