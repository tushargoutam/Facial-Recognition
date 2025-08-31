🧑‍💻 Face Recognition with ResNet50 + Triplet Loss

This project implements a Face Recognition System using Convolutional Neural Networks (CNNs) with Triplet Loss for robust face verification (1:1) and identification (1:N). The system generates embeddings for faces using a ResNet50 backbone and compares them to distinguish identities.

📌 Features

Pre-trained ResNet50 backbone for feature extraction

128-D embedding layer with dropout + L2 regularization

Triplet Loss implementation for training embeddings

Custom triplet generator for dynamic batch creation

Face Verification (check if two images are of the same person)

Face Identification (match an unknown face against a gallery of known faces)

🛠️ Tech Stack

Language: Python 3.x

Libraries: TensorFlow/Keras, OpenCV, NumPy, OS

Model: ResNet50 (ImageNet pre-trained)

Loss Function: Triplet Loss

📂 Dataset

The project uses the Celebrity Faces Dataset (or can be adapted to other face datasets).

Training and test data are structured as:

Celebrity Faces Dataset/
├── Train/
│   ├── Person1/
│   │   ├── img1.jpg
│   │   ├── img2.jpg
│   ├── Person2/
│   │   ├── img1.jpg
│   │   ├── img2.jpg
├── Test/
│   ├── Person1/
│   │   ├── img1.jpg
│   ├── Person2/
│   │   ├── img1.jpg

⚙️ Model Architecture

ResNet50 Backbone (frozen layers)

Flatten → Dense(512, ReLU, L2 Regularization) → Dropout(0.5)

Final Dense(128) embedding layer

🚀 Training

Generate triplets dynamically (Anchor, Positive, Negative).

Optimize embeddings using Triplet Loss.

Train in batches of 32 over multiple epochs.

📊 Evaluation

Face Verification: Compare embeddings of two images → same/different identity.

Face Identification: Match an unknown face against a gallery of known faces.

Example output:

Match: img2.jpg -> Same person (Angelina Jolie). Distance: 0.2341
No Match: img3.jpg -> Different person. Distance: 0.8123

🔐 Applications

Authentication & Access Control

SaaS user verification (KYC, account recovery)

Surveillance & Security Systems

Personalized Recommendations (retail/e-commerce)

EdTech Exam Proctoring

📌 Future Improvements

Fine-tuning ResNet50 for domain-specific datasets

Experiment with ArcFace / CosFace losses for better discriminative embeddings

Bias and fairness evaluation

Deployment with Flask/FastAPI + ONNX Runtime

🤝 Contributing

Pull requests are welcome! For significant changes, please open an issue first to discuss your ideas.

📜 License

This project is licensed under the MIT License.
