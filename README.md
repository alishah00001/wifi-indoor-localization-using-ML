# 🚁 Indoor WiFi Localization using Machine Learning

> A classification project predicting indoor room locations using WiFi signal strengths and evaluating models in both Python and Azure ML.

---


## 📟 Abstract

This project addresses indoor localization using WiFi signal strengths (RSSI values) gathered from different rooms in a building. The goal is to classify which room a signal sample originates from using supervised machine learning techniques. Models including KNN, Decision Tree, and Logistic Regression were trained and evaluated on the dataset. Further, Azure Machine Learning Designer was used to replicate the entire ML pipeline for model deployment and evaluation. The project demonstrates the potential for intelligent room recognition, laying the foundation for automation in smart environments.

---

## 📘 Introduction

Indoor navigation is a challenge for traditional GPS technologies. This project uses a dataset from the UCI Machine Learning Repository that contains 7 WiFi signal strength values (`wifi1` to `wifi7`) and a target label `Room`. Each sample corresponds to a measurement taken from one of several rooms. The dataset is suitable for multiclass classification and consists of over 1,000 labeled records.

### Dataset Reference:

[https://archive.ics.uci.edu/dataset/422/wireless+indoor+localization](https://archive.ics.uci.edu/dataset/422/wireless+indoor+localization)

---

## 🌟 Goal

* Predict the room number based on WiFi signal strengths using classification models.
* Compare the performance of KNN, Decision Tree, and Logistic Regression.
* Identify the best-performing model and justify the selection using performance metrics.
* Demonstrate end-to-end implementation using Azure Machine Learning Designer.
* Provide actionable insights for smart room automation applications.

---

## 💡 Key Novelty

* **Multimodel Approach**: Applies and compares three classification algorithms.
* **Privacy Awareness**: Considers ethical implications of indoor localization and anonymized data use.
* **Smart Automation Potential**: Maps model predictions to IoT-based smart room responses.
* **Cloud Integration**: Rebuilds the ML pipeline in Azure for real-world scalability and deployment.

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis (EDA) & Preprocessing

* Checked for missing values (none found).
* Used `describe()`, histograms, and box plots to understand distributions and detect outliers.
* Standardized the features to prepare for KNN and Logistic Regression.

### 2. Model Training in Python

* **KNN**: Chosen for its non-parametric, distance-based nature.

  * Accuracy: 98%
* **Decision Tree**: Chosen for its ability to handle nonlinear data without scaling.

  * Accuracy: 96%
* **Logistic Regression**: Chosen due to some linear relationships in the data.

  * Accuracy: 98%

### 3. Evaluation

* Confusion matrices and classification reports were generated.
* Metrics used: Accuracy, Precision, Recall, F1-Score
* Logistic Regression outperformed others slightly, with minimal misclassification.

### 4. Azure Machine Learning Designer Implementation

* Recreated pipeline with:

  * Data upload and clean missing values module
  * Normalization
  * Data splitting and training using two models:

    * Multiclass Boosted Decision Tree
    * Multiclass Logistic Regression
* Evaluated models using built-in Azure scoring and evaluation modules.

---

## 📊 Results

### Local Python Model Performance

| Model               | Accuracy | Precision | Recall | F1-Score |
| ------------------- | -------- | --------- | ------ | -------- |
| KNN                 | 98%      | 0.98      | 0.98   | 0.98     |
| Decision Tree       | 96%      | 0.97      | 0.97   | 0.97     |
| Logistic Regression | 98%      | 0.98      | 0.98   | 0.98     |

### Confusion Matrix Insights

* **Logistic Regression**: Misclassifies class 2 occasionally into class 3.
* **Decision Tree**: Slightly more misclassifications than Logistic Regression.

### Azure ML Results

* **Multiclass Boosted Decision Tree** performed better than Logistic Regression across all metrics.
* All steps were documented with screenshots in the Azure pipeline notebook.

---

## 🏣 Business Application

### Primary Purpose

The primary goal of this project is to identify the location of the user within a specific room of a building based on their WiFi signal strength. This enables many business applications, particularly in smart building automation.

### Smart Room Automation

This model can be used to automate room environments. Once a room is predicted by the classification model, the system can trigger specific actions using IoT devices.

#### How It Works

* Integrate the model with IoT devices such as smart lights, thermostats, and speakers via a central hub.
* When the model predicts the user’s room, it sends a signal to activate pre-programmed tasks:

  * **Room 1**: Turn on overhead lights and adjust thermostat to 22°C
  * **Room 2**: Play relaxing music and dim the lights
  * **Room 3**: Switch on a projector for presentations
* Devices respond in real-time based on predictions.

#### Benefits

* Lights automatically turn on when a person enters and off when they leave
* Users can control the climate and ambiance of their room
* Reduces unnecessary energy usage
* Enhances user experience and personalization

### Actionable Recommendations to Leverage Insights

* Use the classification model to predict user location and trigger automations
* Analyze confusion matrix to identify and improve weak areas of prediction
* Ensure devices and apps only activate when needed
* Optimize room utilities for energy efficiency
* Scale system for smart offices, hospitals, or retail environments

---

## 🧠 Conclusion

Logistic Regression showed strong performance in local evaluation, while Boosted Decision Tree was superior in Azure ML. The project successfully demonstrates a real-world use case of ML for indoor localization and highlights how businesses can leverage this for smart building automation.

---

## 📜 License

This project is released under the MIT License.

---


