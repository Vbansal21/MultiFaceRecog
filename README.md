# Real-Time Face Recognition System

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Scope & Novelty](#scope--novelty)
- [Installation](#installation)
- [Usage](#usage)
  - [Registration](#registration)
  - [Recognition](#recognition)
- [Limitations](#limitations)
- [Contributing](#contributing)
- [License](#license)
- [Disclaimer](#disclaimer)

## Introduction

Welcome to the **Real-Time Face Recognition System**, an in-memory face recognition pipeline leveraging state-of-the-art technologies such as **CLIP** for embedding extraction, **FAISS** for efficient similarity search, and **Forward-Forward (FF) Learning** for dynamic model updates. This project is designed for archival purposes and may not receive future updates.

## Features

- **Face Detection**: Utilizes **MTCNN** for robust face detection in images and videos.
- **Embedding Extraction**: Employs **CLIP (from Hugging Face)** to generate high-dimensional embeddings for detected faces.
- **Similarity Search**: Integrates **FAISS** for fast and scalable similarity searches within the embedding space.
- **Forward-Forward Learning**: Implements a novel **Forward-Forward** learning mechanism to update the model using positive and negative examples without traditional backpropagation.
- **Spoof Detection**: Incorporates a basic blink-based spoof detection system to enhance liveness checks.
- **In-Memory Storage**: Maintains all student registrations and embeddings in-memory using Python dictionaries, eliminating the need for external databases.
- **Flexible Input Sources**: Supports face registration and recognition using single images, folders of images, or video files, facilitating easy demonstrations without relying on a webcam.

## Scope & Novelty

### Scope

This project aims to provide a streamlined and efficient face recognition system suitable for educational, demonstration, or archival purposes. By focusing on in-memory operations, it simplifies deployment and usage without the overhead of database management.

### Novelty

- **Forward-Forward Learning Integration**: Unlike traditional backpropagation-based models, this system employs **Forward-Forward Learning**, allowing for continuous and incremental updates based on positive and negative examples. This approach can potentially offer more flexible and adaptable learning mechanisms.
- **Combination of CLIP and FAISS**: Leveraging **CLIP** for rich embedding generation combined with **FAISS** for rapid similarity searches creates a powerful pipeline for face recognition tasks.
- **Spoof Detection Mechanism**: The inclusion of a blink-based spoof detection adds a layer of security, ensuring that only live faces are recognized, thereby mitigating basic spoofing attempts.

## Installation

### Prerequisites

- **Python 3.7+**
- **pip** package manager

### Dependencies

Ensure you have the following packages installed.

```plaintext
opencv-python
numpy
torch
transformers
faiss-cpu
mediapipe
easyocr
facenet-pytorch
```

### Setting Up

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/face-recognition-system.git
   cd face-recognition-system
   ```

2. **Install Dependencies**

   ```bash
   pip install facenet-pytorch mediapipe faiss-cpu opencv-python-headless numpy matplotlib transformers torch torchvision
   ```

3. **Download Models**

   Ensure that all required models (e.g., CLIP from Hugging Face) are downloaded as part of the initial setup or are automatically fetched when running the code.

## Usage

### Registration

Register a new student by providing a registration number, name, and an input source (single image, folder of images, or video).

```python
from your_module import register_student_from_source

# Example: Register using a single image
register_student_from_source(
    reg_no="1234",
    name="Ryan Gosling",
    input_source="path/to/ryanG_1.jpg"
)

# Example: Register using a folder of images
register_student_from_source(
    reg_no="5678",
    name="Emma Stone",
    input_source="path/to/emma_folder/"
)

# Example: Register using a video file
register_student_from_source(
    reg_no="9101",
    name="Chris Evans",
    input_source="path/to/chris_video.mp4"
)
```

### Recognition

Recognize faces by providing an input source (single image, folder of images, or video).

```python
from your_module import recognize_faces_from_source

# Example: Recognize using a single image
recognize_faces_from_source(
    input_source="path/to/ryanG_2.jpg",
    faiss_dist_threshold=0.2
)

# Example: Recognize using a folder of images
recognize_faces_from_source(
    input_source="path/to/test_images_folder/",
    faiss_dist_threshold=0.2
)

# Example: Recognize using a video file
recognize_faces_from_source(
    input_source="path/to/test_video.mp4",
    faiss_dist_threshold=0.2
)
```

**Note**: Ensure that the `faiss_dist_threshold` is set appropriately to balance between recognition accuracy and tolerance for similarity distances.

## Limitations

- **In-Memory Storage**: All registrations and embeddings are stored in-memory, making the system unsuitable for large-scale deployments or scenarios requiring persistent storage.
- **Spoof Detection**: The current spoof detection mechanism is rudimentary, relying solely on blink detection. Advanced spoofing techniques might bypass this security layer.
- **Forward-Forward Learning**: While innovative, Forward-Forward Learning is less established compared to traditional backpropagation methods. Its effectiveness in various scenarios needs further validation.
- **No Real-Time Processing**: Although designed for real-time recognition, processing speed is contingent on hardware capabilities and input source complexity.
- **Limited Error Handling**: The system may encounter issues with malformed inputs or unsupported file formats without comprehensive error management.

## Contributing

This project is for archival purposes and may not receive updates. However, contributions are welcome. Feel free to fork the repository and submit pull requests for enhancements or bug fixes.

## License

This project is licensed under the [MIT License](LICENSE).

## Disclaimer

**Archived Project**: This code was developed for archival purposes and may **not** receive future updates or maintenance. Use it at your own discretion. The author(s) make no guarantees regarding its functionality, security, or suitability for any purpose.

---

*Developed by [Vaibhav Bansal](https://github.com/Vbansal21) (and team) in Sem-2, session 2022-2023.*

---

README generated with ChatGPT.
