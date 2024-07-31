# Heart-rate-ECG-Heart-Rate-Classification-(98%,accuracy-recall)

## What is an ecg?

An electrocardiogram (ECG) is a simple test that can be used to check your heart's rhythm and electrical activity.

Sensors attached to the skin are used to detect the electrical signals produced by your heart each time it beats.

These signals are recorded by a machine and are looked at by a doctor to see if they're unusual.

An ECG may be requested by a heart specialist (cardiologist) or any doctor who thinks you might have a problem with your heart, including your GP. That's the result of this test we will analyze.


## ECG Heart Rate Classification
This project aims to classify ECG heart rate data as normal or abnormal using a neural network model. The data used in this project is a combination of the mitbih_train.csv and mitbih_test.csv datasets.

## Dataset
The combined dataset has five classes:

N: Normal beat (Class 0)
S: Supraventricular premature beat (Class 1)
V: Premature ventricular contraction (Class 2)
F: Fusion of ventricular and normal beat (Class 3)
Q: Unclassified beat (Class 4)


### Objective
The objective is to build a model that can predict whether an ECG heart rate is normal[0] or abnormal[1].


### Data Imbalance Issue
The original dataset exhibited an imbalance between classes:
![image](https://github.com/user-attachments/assets/56f4140e-5a85-45f0-95cf-1cff78c0b47d)

Class 0 (Normal beat): 90,589 samples
Class 1 (Supraventricular premature beat): 18,857 samples
To address this issue, data augmentation was employed:

Downsampling: Reduced the number of samples in Class 0 from 90,589 to 60,000.
Upsampling: Increased the number of samples in Class 1 from 18,857 to 30,000 by adding noise.

![image](https://github.com/user-attachments/assets/3dced969-7137-4fb9-b9ea-713b5c2e05a2)

#### Why Data Augmentation is Okay ?
Data augmentation, such as adding noise, is a common technique used to address class imbalance. It helps in:

Balancing Classes: Ensures that the model is trained on a more balanced dataset, which can improve generalization.
Avoiding Overfitting: Prevents the model from being biased towards the majority class.
Improving Model Performance: Enhances the model's ability to recognize and classify underrepresented classes.
By adding noise to the samples of Class 1, the variability is increased, making the model more robust to variations within that class.


### Model
A simple fully connected neural network with three layers was used for this task. Below are the details of the model architecture and the results obtained.

#### Model Architecture
Input Layer: Dense layer with 128 units, ReLU activation
Hidden Layer 1: Dense layer with 64 units, ReLU activation
Hidden Layer 2: Dense layer with 16 units, ReLU activation
Output Layer: Dense layer with 1 unit, sigmoid activation

#### Compilation
The model is compiled with the following configuration:

Loss Function: Binary cross-entropy
Optimizer: Adam
Metrics: Accuracy, Precision, Recall

##### Random Forest
A Random Forest Classifier was used as a traditional machine learning approach.



## Results

##### Before Data Augmentation:

![image](https://github.com/user-attachments/assets/b8c0150d-5d2d-4115-a2b2-0154d0e0ab6b)


##### After Data Augmentation:

![image](https://github.com/user-attachments/assets/d5d06e37-2dfa-4acd-b4df-b4609ba2af2c)

There is a noticeable improvement (Especially in class 1) .!!

##### Random Forest
![image](https://github.com/user-attachments/assets/f2738deb-ac86-489f-bbc7-94e677f4e9f3)


## Contributing
If you would like to contribute to this project, please fork the repository and submit a pull request. For major changes, please open an issue to discuss what you would like to change.








