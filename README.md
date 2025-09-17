# Fake Social Media Account Detection using ANN and Data Augmentation 🕵️‍♂️

This project implements a deep learning model to effectively predict whether a social media account, with a focus on Instagram, is fake or genuine. The system is designed to improve detection accuracy through data augmentation and is deployed as a user-friendly web interface.

The core of this project is an **Artificial Neural Network (ANN)** that learns to distinguish between real and fake profiles by analyzing various account attributes. To enhance the model's robustness and generalization, the training dataset is expanded using augmentation techniques like **flipping, jitter, and feature scaling**. The final model is integrated into a Flask-based web application where users can input profile details to check for authenticity.



---

## 📋 Key Features

* **Fake Account Detection**: Classifies social media profiles as "Fake" or "Genuine".
* **Artificial Neural Network (ANN)**: Utilizes a four-layer ANN to learn the complex patterns of fake accounts.
* **Data Augmentation**: Employs techniques like Random Jitter, Scaling, Swapping, and Flipping to create a more diverse training set, significantly improving model performance.
* **High Accuracy**: Achieves **93% accuracy** and reduces validation loss by over 10% after data augmentation.
* **Web Interface**: An interactive front-end built with Flask allows users to easily input account metrics for verification.

---

## ⚙️ Project Workflow

The project follows a systematic workflow from data exploration and preparation to model deployment, as illustrated in the paper.

1.  **Data Exploration**: The process starts with a structured dataset of 600 Instagram profiles from Kaggle, containing attributes like profile picture status, username length, follower/following counts, etc.
2.  **Data Normalization**: The numerical features in the dataset are scaled using **MinMax Scalar** and **Standard Scalar** to ensure they are within a consistent range for the neural network.
3.  **Data Augmentation**: To improve the model's ability to generalize, the normalized training data is augmented to generate additional, varied samples.
4.  **ANN Model Development**: An ANN is built and trained on the prepared dataset.
5.  **Cross-Validation & Testing**: The model is trained and tested using an 80:20 data split to evaluate its performance and prevent overfitting.
6.  **Web Interface**: The trained ANN model is deployed in a Flask web application, providing a user-friendly interface for predictions.

---

## 🧠 Model Architecture

The Artificial Neural Network (ANN) is designed to effectively classify accounts based on their profile data.

* **Input Layer**: Accepts 11 input features from the normalized dataset.
* **Hidden Layers**: Consists of three hidden layers with **100, 50, and 25 neurons** respectively, all using the **ReLU** activation function.
* **Dropout Layers**: Three dropout layers with a rate of **0.1** are placed between the dense layers to prevent overfitting.
* **Output Layer**: A final dense layer with a **Softmax** activation function to output the class probabilities (Fake or Genuine).
* **Compilation**: The model is compiled using the **Adam optimizer** and the **categorical cross-entropy** loss function, with accuracy as the primary evaluation metric.



---

## 📊 Results

A key finding of this research is the significant improvement in model performance after applying data augmentation. The model's ability to correctly classify accounts and balance precision with recall was drastically enhanced.

The confusion matrix also shows a marked improvement in correctly identifying both true positives and true negatives after augmentation.



---

## 🛠️ Technologies Used

* **Backend**: Python, Flask
* **Deep Learning**: TensorFlow, Keras
* **Data Processing**: Pandas, NumPy, Scikit-learn

---

## 🚀 Getting Started

### Prerequisites
* Python 3.8+
* Pip

### Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/fake-account-detection.git](https://github.com/your-username/fake-account-detection.git)
    cd fake-account-detection
    ```

2.  **Create a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Flask application:**
    ```bash
    python app.py
    ```

5.  Open your web browser and navigate to `http://127.0.0.1:5000` to access the application.

---

## 💻 How to Use

1.  Navigate to the home page of the web application.
2.  Enter the numerical or binary (0/1) details for the Instagram profile you want to check, based on the input fields provided (e.g., Profile Picture, Nums/Length Username, Number of Followers, etc.).
3.  Click the **"Check Account Authenticity"** button.
4.  The system will process the inputs and display the prediction: whether the account is likely "Fake" or "Genuine."

---

