# 🔍 YOLOv11 Image Search Application

A powerful **Computer Vision-based Image Search App** built using **YOLOv11 + Streamlit**. This application allows users to detect objects in images and search images intelligently using object-based filters.

---

## 🚀 Features

* ✅ Object detection using YOLOv11
* ✅ Search images using detected objects
* ✅ OR / AND search modes
* ✅ Threshold-based filtering
* ✅ Interactive UI with Streamlit
* ✅ Bounding box visualization
* ✅ Export results as JSON
* ✅ Grid layout display

---

## 🧠 How It Works

1. Run YOLO model on images
2. Generate metadata (JSON format)
3. Extract:

   * Object classes
   * Counts
   * Bounding boxes
4. Perform search queries on metadata
5. Display filtered results

---

## 🖼️ UI Flow

### 🔹 Flow 1: Data Processing

* Load metadata OR process new images
* Run YOLO inference
* Save metadata

### 🔹 Flow 2: Search System

* Select classes
* Choose search mode (OR / AND)
* Apply thresholds
* Get results

### 🔹 Flow 3: Visualization

* Show images in grid
* Draw bounding boxes
* Highlight matches
* Export results

---

## 📂 Project Structure

```
Yolo_image_search/
│
├── app.py
├── requirements.txt
├── metadata.json
│
├── configs/
│   └── default.yaml
│
├── src/
│   ├── inference.py
│   ├── utils.py
│   └── config.py
│
├── model/
│   └── yolo11m.pt
│
└── data/
    ├── raw/
    └── processed/
```

---

## ⚙️ Installation

### 🔹 Create Environment

```
conda create -n yolo_image_search python=3.11 -y
conda activate yolo_image_search
pip install -r requirements.txt
```

---

### 🔹 GPU Setup (Optional)

```
conda create -n yolo_image_search_gpu python=3.11 -y
conda activate yolo_image_search_gpu
conda install pytorch==2.5.1 torchvision==0.20.1 pytorch-cuda=12.4 -c pytorch -c nvidia
pip install -r requirements.txt
```

---

## 📥 Download Model

This project uses YOLOv11 pre-trained weights.

🔗 Download the model from:
https://github.com/ultralytics/ultralytics

📁 After downloading, place the file in the root directory of the project:

yolo11m.pt

⚠️ Note:
The model file is not included in this repository due to its large size.

## ▶️ Run Application

```
streamlit run app.py
```

App runs on: http://localhost:8501

---

## 🔍 Usage

### Option 1: Process New Images

* Enter image directory
* Provide model path (`yolo11m.pt`)
* Click **Start Inference**

### Option 2: Load Metadata

* Provide `metadata.json` path
* Click **Load Metadata**

---

## 🎯 Search Features

### Search Mode

* **OR** → Any selected class
* **AND** → All selected classes

### Filters

* Class selection
* Object count thresholds

### Display Options

* Grid layout
* Show bounding boxes
* Highlight matches

---

## 📊 Metadata Format

```
{
  "image_path": "...",
  "detections": [
    {
      "class": "person",
      "confidence": 0.92,
      "bbox": [x1, y1, x2, y2],
      "count": 3
    }
  ],
  "total_objects": 5,
  "unique_class": ["person", "car"],
  "class_counts": {
    "person": 3,
    "car": 2
  }
}
```

---

## ⚙️ Configuration

```
model:
  yolo_model: "yolo11m.pt"
  conf_threshold: 0.3

data:
  image_extension: [".jpg", ".jpeg", ".png"]
```

---

## 🧩 Core Components

* **Inference Engine** → YOLO-based object detection
* **Utils Module** → Metadata handling & filtering
* **Config Loader** → YAML-based configuration

---

## 📦 Tech Stack

* Python
* Streamlit
* YOLO (Ultralytics)
* OpenCV
* PyTorch

---

## 🚀 Future Improvements

* FastAPI backend integration
* Deployment (Streamlit Cloud / Render)
* Add authentication system
* Improve search ranking
* Add real-time camera input

---

## 👨‍💻 Author

**Manish Bhagat**

---

## ⭐ Support

If you like this project, consider giving it a ⭐ on GitHub!
