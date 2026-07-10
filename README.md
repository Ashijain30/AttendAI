# 🎥 AttendAI — Real-Time Facial Recognition Attendance System

A real-time attendance system that uses facial recognition via webcam to automatically 
detect, recognize, and log attendance — eliminating manual roll calls and enabling 
contactless, fast, and accurate tracking.

## 🔧 Tech Stack
- **Language:** Python
- **Computer Vision:** OpenCV, face-recognition library
- **Database:** SQLite
- **Voice Feedback:** pyttsx3
- **Reporting:** python-docx (auto-generated Word reports), CSV export

## ✨ Features
- **Real-time face detection & recognition** via webcam
- **Two registration modes:**
  - Manual: capture via webcam or upload photo through a GUI (`register.py`)
  - Bulk: enroll multiple users at once from a folder of images (`bulk_register.py`)
- **Voice welcome message** on successful recognition (via pyttsx3)
- **Automatic attendance logging** to a SQLite database with timestamps
- **Auto-generated daily CSV attendance reports**
- **One-click professional Word report generation** summarizing the project (`generate_report.py`)

## 🚀 How It Works
1. Users are registered (manually or in bulk) — their face is encoded and stored 
   (`encodings.pickle`) along with their details in the SQLite database
2. `main.py` starts the webcam and continuously matches live faces against stored encodings
3. On a match, the system marks the user "Present" in the database and plays a voice greeting
4. On exit, a daily CSV attendance report is automatically generated and opened
5. A professional Word document summarizing the system can be generated anytime via `generate_report.py`

## 🖥️ Setup & Usage

**1. Install dependencies:**
```bash
pip install opencv-python face-recognition pyttsx3 python-docx numpy
```

**2. Register users:**
- Manual: `python register.py` (webcam capture or image upload via GUI)
- Bulk: place images in a folder and run `python bulk_register.py`

**3. Run the system:**
```bash
python main.py
```
The webcam opens; recognized faces are marked present with a voice welcome. 
Press `q` to exit — a daily CSV report is auto-generated.

**4. Generate reports:**
- Daily CSV: auto-created by `main.py`, or manually via `python export_attendance.py`
- Full project report (Word doc): `python generate_report.py`

## 📌 Future Improvements
- Add liveness detection to prevent spoofing via photos
- Web-based dashboard for viewing attendance trends over time
