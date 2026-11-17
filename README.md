# Autonomous Driving Perception & Intelligence System (ADAS)

An AI-powered autonomous driving perception platform designed to demonstrate road-scene understanding through object detection, object tracking, lane detection, depth estimation and driving simulation.

## Project Overview

The Autonomous Driving Perception & Intelligence System combines computer vision, deep learning and backend APIs to process road images and videos and provide perception-related information.

The project includes a web dashboard for interacting with the perception modules and monitoring the system.

## Live Application

**Live Dashboard:**  
https://adas-autonomous-driving.onrender.com/simulation

**GitHub Repository:**  
https://github.com/Mymudh/autonomous-driving-ai

## Key Features

- **Object Detection:** YOLO-based vehicle and object detection.
- **Object Tracking:** ByteTrack-based tracking implementation.
- **Lane Detection:** OpenCV-based road lane detection.
- **Depth Estimation:** MiDaS-based depth estimation implementation.
- **Video Analysis:** Road-video processing interface.
- **Driving Simulation:** Interactive autonomous-driving simulation dashboard.
- **Performance Monitoring:** API endpoints for performance information.
- **REST API:** Flask backend for perception services.
- **Web Dashboard:** React-based frontend.

## Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python, JavaScript |
| Backend | Flask, Flask-CORS |
| Frontend | React, Vite |
| Object Detection | YOLO, Ultralytics |
| Object Tracking | ByteTrack |
| Computer Vision | OpenCV |
| Depth Estimation | MiDaS |
| Deep Learning | PyTorch, Torchvision |
| Visualization | Recharts |
| Model Optimization | ONNX |
| Simulation | CARLA integration code, ROS 2 integration code |
| Version Control | Git, GitHub |

## Project Architecture

```text
autonomous-driving-ai-main/
│
├── backend/
│   ├── app.py
│   ├── config.py
│   ├── requirements.txt
│   ├── models/
│   ├── routes/
│   ├── services/
│   └── tests/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── services/
│   ├── package.json
│   └── vite.config.js
│
├── model_training/
│   ├── bdd100k_to_yolo.py
│   ├── export_model.py
│   ├── train_enet.py
│   ├── train_yolo.py
│   └── README.md
│
├── simulation/
│   ├── carla_perception_agent.py
│   └── ros2/
│
├── docs/
├── README.md
├── render.yaml
└── start.bat
```

## Installation and Setup

### Prerequisites

- Python 3.11
- Node.js and npm
- Git
- PyCharm or another Python IDE

### 1. Clone the Repository

```bash
git clone https://github.com/Mymudh/autonomous-driving-ai.git
```

```bash
cd autonomous-driving-ai/autonomous-driving-ai-main
```

### 2. Create Python Virtual Environment

```bash
python -m venv venv
```

Activate on Windows:

```powershell
venv\Scripts\activate
```

### 3. Install Backend Dependencies

```bash
cd backend
```

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Review the `.env.example` file and configure the required environment variables.

Do not upload API keys, passwords or database credentials to GitHub.

### 5. Start Backend

```bash
python app.py
```

Backend URL:

```text
http://127.0.0.1:5000
```

### 6. Install Frontend Dependencies

Open another terminal:

```bash
cd frontend
```

```bash
npm install
```

### 7. Start Frontend

```bash
npm run dev
```

Open the Vite URL displayed in the terminal, usually:

```text
http://localhost:5173
```

## API Endpoints

The Flask backend exposes the following endpoints:

| Endpoint | Purpose |
|---|---|
| `/api/` | API information |
| `/api/health` | Health status |
| `/api/detect/image` | Image detection |
| `/api/detect/video` | Video detection |
| `/api/track/video` | Video tracking |
| `/api/lane/detect` | Lane detection |
| `/api/depth/estimate` | Depth estimation |
| `/api/performance` | Performance information |
| `/api/model/info` | Model information |
| `/api/ros2/status` | ROS 2 status |
| `/api/simulation/status` | Simulation status |

## Dataset Preparation

The project includes dataset preparation and training scripts intended for autonomous-driving datasets such as:

- BDD100K
- KITTI

Dataset preparation and training should be performed using the appropriate dataset files and configuration.

## Model Training

The repository includes scripts for:

- YOLO model training
- Lane segmentation training
- Dataset conversion
- Model export

A trained YOLO checkpoint named `best.pt` is required for the configured object-detection service.

Place the compatible trained checkpoint in:

```text
backend/models/best.pt
```

Do not use an empty or placeholder model file.

## Testing and Evaluation

The system provides API endpoints and modules for testing perception functionality.

Recommended evaluation metrics:

- Object detection: Precision, Recall and mAP
- Object tracking: IDF1 and tracking accuracy
- Lane detection: IoU and lane detection accuracy
- Depth estimation: MAE and RMSE
- Performance: FPS and inference time

Record actual measurements from completed tests before reporting numerical results.

## Current Limitations

- The trained YOLO checkpoint must be supplied separately.
- MongoDB must be configured and running for database-dependent functionality.
- CARLA and ROS 2 integrations require their respective environments and testing.
- ONNX export and inference performance require validation.
- TensorRT execution requires compatible NVIDIA hardware and software.
- Some advanced features may require additional model training and configuration.

## Future Improvements

- Improve object detection accuracy using larger driving datasets.
- Integrate real-time vehicle tracking.
- Improve lane detection under different weather and lighting conditions.
- Integrate and validate CARLA simulation.
- Complete ROS 2 communication.
- Optimize model inference using ONNX.
- Evaluate real-time performance on supported hardware.

## Project Status

The Flask backend and React dashboard have been deployed. The API health endpoint has been verified locally.

Individual AI modules and advanced simulation integrations require further validation before being considered fully operational.

## Author

**Shaik Maimood**

GitHub: https://github.com/Mymudh

Project: Autonomous Driving Perception & Intelligence System
