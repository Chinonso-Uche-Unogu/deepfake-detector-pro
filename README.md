# 🛡️ Deepfake Detector Pro
**Developed by [Chinonso Uche Unogu](https://github.com/Chinonso-Uche-Unogu)**

[![Hugging Face Space](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/UCnino/deepfake-detector-pro)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-green.svg)](https://opensource.org/licenses/Apache-2.0)

## 📌 Overview
**Deepfake Detector Pro** is a computer vision tool built to combat synthetic media in 2026. Leveraging the **SigLIP-2 (Vision Transformer)** architecture, the system identifies pixel-level inconsistencies and structural artifacts typical of AI-generated content.

Initially developed for static image classification, I scaled this version to include a **custom temporal sampling engine** to analyze video files.

## ⚙️ Technical Architecture
The application follows a modular pipeline to ensure high accuracy while maintaining low inference latency on CPU infrastructure:

1. **Preprocessing:** Images are normalized and resized using the `AutoImageProcessor`.
2. **Video Engine:** For `.mp4` and `.avi` files, the system implements a **5-frame sampling logic** via OpenCV to detect temporal anomalies.
3. **Inference:** Tensors are passed through the `Deep-Fake-Detector-v2-Model` (ViT) to generate logits.
4. **Post-processing:** Softmax activation provides a confidence score for `Realism` vs. `Deepfake`.

## 🚀 Deployment
The project is containerized and hosted on **Hugging Face Spaces**.
* **Framework:** Gradio 5.x
* **Backend:** PyTorch
* **Computer Vision:** OpenCV (cv2)

## 🛠️ Installation & Local Usage
```bash
# Clone the repository
git clone [https://github.com/Chinonso-Uche-Unogu/deepfake-detector-pro.git](https://github.com/Chinonso-Uche-Unogu/deepfake-detector-pro.git)

# Enter the directory
cd deepfake-detector-pro

# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
