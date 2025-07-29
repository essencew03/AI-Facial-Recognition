
# Facial Recognition & Tracking System

This project (`facial_demo`) implements **real-time face recognition and tracking** using:
✅ **InsightFace** – face detection & embeddings
✅ **DeepSORT** – multi-object tracking
✅ **TorchReID** – body re-identification

It can **recognize known people** (from the `dataset/` folder) and **assign IDs to unknown individuals**.

---

## 📂 Project Structure

```
facial_demo/
│── dataset/
│   ├── David_Deprospero/       # Images of David
│   ├── Essence_Wallace/        # Images of Essence
│
│── main.py                     # Basic facial recognition using embeddings
│── face_tracker.py             # Face recognition + DeepSort + ReID
│── requirements.txt            # Dependencies
│── README.md
```

---

## 📦 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/facial_demo.git
cd facial_demo
```

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Prepare Dataset

Inside the `dataset/` folder, create **one subfolder per person** and add **several clear images**:

```
dataset/
│── David_Deprospero/ 
│   ├── img1.jpg
│   ├── img2.jpg
│
│── Essence_Wallace/
│   ├── img1.jpg
│   ├── img2.jpg
```

---

## ▶️ Usage

### **Run Basic Recognition (`main.py`)**

Compares embeddings from the dataset to the live camera feed.

```bash
python main.py
```

### **Run Recognition + Tracking (`face_tracker.py`)**

Uses DeepSORT and TorchReID for real-time tracking and consistent IDs.

```bash
python face_tracker.py
```

---

## 📊 How It Works

🔹 **main.py**
✔ Loads dataset embeddings for David & Essence
✔ Uses cosine similarity for recognition
✔ Assigns "UnknownX" IDs for new faces

🔹 **face_tracker.py**
✔ Uses DeepSORT for multi-person tracking
✔ Uses TorchReID to extract body features
✔ Keeps IDs consistent even if faces leave the frame

---

## 🛠 requirements.txt

Use the following pinned dependencies for compatibility:

```txt
opencv-python==4.10.0.84
numpy==1.26.4
insightface==0.7.3
scikit-learn==1.5.0
torch==2.3.0
torchvision==0.18.0
torchaudio==2.3.0
torchreid==0.2.5
deep-sort-realtime==1.3.2
```

Install with:

```bash
pip install -r requirements.txt
```

---

## 🚀 Future Improvements
🔹 Robot Following Mode – Allow a robot dog to follow a specific recognized person.
🔹 Gesture Commands – Use facial recognition + hand gestures for robot dog commands.
🔹 Autonomous Patrol – Robot dog patrols and alerts when an unknown person is detected.
🔹 Navigation System – Integrate with SLAM so the robot dog can move toward recognized people.
