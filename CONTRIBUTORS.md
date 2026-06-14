# Project Contributors - Real-Time Multimodal Emotion Detection

This repository houses the collaborative work of our development group. To ensure proper credit, attribution, and visibility for all team members, this document serves as the official registry of contributions for our **Real-Time Multimodal Emotion Detection Pipeline (YOLO + ViT + Spark Streaming)**.

---

## 👥 Meet the Team

| Team Member | GitHub Profile | Core Focus & Responsibilities |
| :--- | :--- | :--- |
| **Vignesh V S (Vignesh Saminathan)** | [@VigneshVS2005](https://github.com/VigneshVS2005) | Project Owner, YOLO/ViT Model Architecture & Spark Union Streaming |
| **Karthick Ruban** | [@Karthickruban](https://github.com/Karthickruban) | Scala Image Preprocessing, HDFS Optimization, & Columnar Parquet |
| **Hariprakash** | [@Hariprakash024](https://github.com/Hariprakash024) | Real-time Webcam Edge Producers, Face Localization, OpenCV |
| **Sanjay Senthil** | [@sanjaysenthil17](https://github.com/sanjaysenthil17) | Medallion Pipeline (Bronze/Silver/Gold), KPIs, & Validation |

---

## 📊 Detailed Contribution Matrix

Our multimodal big-data pipeline was divided into the following architectural components:

### 1. Edge Camera Producers (YOLO & ViT Inference)
*   **Hariprakash**: Integrated OpenCV camera captures and configured real-time inference wrappers. Wrote the Euclidean matching trackers to assign stable person IDs on the edge.
*   **Vignesh V S**: Tuned and trained the YOLO model on custom datasets. Integrated the Vision Transformer (ViT) emotion model with Grad-CAM overlays.

### 2. Big Data Ingestion (Scala & HDFS)
*   **Karthick Ruban**: Programmed the Scala job (`xyz.scala`) to read dataset images, convert them to binary bytes, attach labels, and save them as compressed Snappy Parquet shards on HDFS.
*   **Hariprakash**: Structured the HDFS directories and mapped input nodes to handle high-speed parallel reads.

### 3. Spark Structured Streaming (Medallion Architecture)
*   **Vignesh V S**: Developed the core streaming script (`spark_vit_yolo_streaming.py`) to parse JSON streams and union inputs from YOLO and ViT edge devices.
*   **Sanjay Senthil**: Designed the Medallion layers:
    *   *Bronze*: Raw event capture (preserving source IDs and timestamps).
    *   *Silver*: Confidence filtering and schema cleaning.
    *   *Gold*: Aggregated windowed metrics (top-k emotions per device, sliding window counts).

### 4. Pipeline Testing & KPIs Validation
*   **Sanjay Senthil**: Verified aggregate states and memory allocations via the Spark Web UI.
*   **Karthick Ruban**: Monitored execution parallelism across driver/executor nodes on the Amrita cluster.

---

## 🌟 How Teammates Can Showcase This Project on Their Profiles

To display this project on your personal GitHub profile page:

### Step 1: Fork the Repository
1.  Navigate to the original repository: `https://github.com/VigneshVS2005/Real-Time-Multimodal-Emotion-Detection-with-YOLO-ViT-and-Spark-Streaming`
2.  Click the **Fork** button in the top right corner.
3.  This creates a clone under your account (e.g. `github.com/Karthickruban/Real-Time-Multimodal-Emotion-Detection-with-YOLO-ViT-and-Spark-Streaming`).

### Step 2: Pin the Project
1.  Go to your personal GitHub profile page.
2.  Under the **Pinned** section, click **Customize your pins**.
3.  Select `Real-Time-Multimodal-Emotion-Detection-with-YOLO-ViT-and-Spark-Streaming` (your fork) and click **Save**.

### Step 3: Accept the Collaborator Invitation
1.  Open the email invitation sent by the repository owner, or navigate to `https://github.com/VigneshVS2005/Real-Time-Multimodal-Emotion-Detection-with-YOLO-ViT-and-Spark-Streaming/invitations` to accept the invite.
2.  Once accepted, you are officially logged as an owner/collaborator, and your contributions will count directly towards your public activity metrics.
