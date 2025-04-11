# 🎯 AI-powered Voice-Assisted Object Locator (AIVOL)

> 👁️ Designed to assist visually impaired individuals in locating everyday objects using voice commands, real-time computer vision, and natural language processing — all running on a Raspberry Pi 5.

---

## 👥 Team Members

- Het Bharatkumar Patel (Maintainer of this fork)
- Parth Dadhania
- Chinmoy Sahoo
- Dang Nguyen

---

## 🔑 Core Features

✅ Wake word functionality (“Hey Assistant”) to trigger voice command flow  
✅ End-to-end integration of speech recognition, object detection, text-to-speech and real-time feedback  
✅ Real-time object locating and directional guidance  
✅ NLP-powered query understanding (e.g., “Where is my red cup on the table?”)  
✅ Handles missing objects with fallback suggestions  
✅ Lightweight and plug-and-play setup  
✅ Works seamlessly on both WSL and Raspberry Pi OS

---

## 🧠 How It Works

1. **Wake Word Detection** – Listens for the keyword “Hey AIVOL” before capturing commands
2. **Voice Recognition** – Captures user’s voice query using Google Speech Recognition  
3. **NLP Parser** – Processes the text to extract object descriptors (name, color, location) using spaCy/NLTK  
4. **Object Detection** – Scans the environment using YOLOv5m with Objects365 dataset  
5. **Filtering & Reasoning** – Filters objects based on query relevance and WordNet synonyms
6. **Text-to-Speech** – Provides real-time guidance (e.g., "Move slightly left") using `gTTS`
7. **Continuous Guidance** – Tracks movement and updates directions while user moves using Mediapipe

---

## 📽️ Working Demo

🎥 **Watch the full working prototype demo here:**  
[📺 AIVOL Demo Video](https://drive.google.com/file/d/12i0sUYGtml0EsvSWSRfKyyfh2CM3sd4P/view?usp=sharing)

---

## 🧰 Tech Stack

| Layer | Technologies |
|------|--------------|
| 💻 Hardware | Raspberry Pi 5 (16GB RAM, 128GB Storage), 120° FoV USB Camera, Logitech USB Headset |
| 🧠 AI Models | YOLOv5m (trained on Objects365), Mediapipe |
| 🗣️ Voice | Google Speech Recognition, PyAudio, gTTS |
| 🧾 NLP | spaCy, NLTK, WordNet |
| 🐍 Programming | Python 3.11.4 |
| ⚙️ Deployment | WSL (Dev), Raspberry Pi OS (Prod) |
| 🔧 Setup | Bash, `setup.sh`, `requirements.txt` |

---

## 🚀 Setup Instructions

### 📦 Clone the Repository

```bash
git clone https://github.com/HetP1742431/AI-Powered-Voice-Assisted-Object-Locator.git
cd AI-Powered-Voice-Assisted-Object-Locator
```

### ⚙️ Run the Setup Script

```bash
chmod +x setup.sh
./setup.sh
```

This will:
- Install system dependencies
- Install Python 3.11.4 via pyenv
- Create and activate a virtual environment
- Install all Python dependencies
- Download YOLOv5m weights

### ✅ Run the Project

```bash
python3 src/main.py
```

## 📋 Sample Usage Flow

User: "Hey Assistant, where is my black wallet?"
🧠 → Extracts: object=wallet, color=black
🎯 → Scans environment and detects object
🎙️ → Speaks: "Your black wallet is on the table, slightly to your left."

## 📈 Outcomes

- ✅ Successfully detects and filters household objects in cluttered scenes
- ✅ Accurate directional feedback with >90% recognition accuracy indoors
- ✅ Lightweight, end-to-end working prototype using affordable components
- ✅ Low setup time and portable form factor for real-world deployment

## 💡 What I Learned
- 📦 Gained hands-on experience with hardware-software integration using Raspberry Pi 5
- 🧠 Learned to build and optimize real-time object detection pipelines using YOLOv5 and OpenCV
- 🗣️ Understood the nuances of voice-to-intent mapping using spaCy, NLTK, and WordNet
- 🧪 Practiced modular, testable Python design and deployment automation
- 🔄 Improved debugging, cross-platform compatibility, and performance optimization for edge devices
- 🎯 Gained confidence in translating user-centric problems into full-stack intelligent systems
