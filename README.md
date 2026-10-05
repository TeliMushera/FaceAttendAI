# FaceAttend AI

FaceAttend AI is a student attendance system that uses webcam-based face recognition to identify registered students and mark attendance automatically.

## Project Overview

This project is built to reduce manual attendance work in classrooms. Instead of writing names or checking attendance sheets, the system captures a live face from the webcam, compares it with stored student face data, and marks the student as present if the match is valid.

The main idea is simple:
- register student details and photo
- save the face data
- detect face from webcam
- compare it with registered faces
- mark attendance when the match is correct

## Main Logic / Workflow

```text
+----------------------------------------------------+
|                    FaceAttend AI                   |
|             Workflow & Main Logic                  |
+----------------------------------------------------+

1. Register Student
   ├── Student Details
   │   • Student ID
   │   • Name
   │   • Department
   │   • Email
   ├── Photo Upload
   │   • image is saved in student_photos/
   └── Stored in SQLite database

   ↓

   OpenCV detects face
   ↓
   FaceNet512 creates embedding
   ↓
   Registered embedding stored in memory/database

2. Live Attendance (Webcam)
   ├── Webcam Frame
   │   • streamlit-webrtc
   ├── Detect Face
   │   • OpenCV Haar Cascade
   ├── FaceNet512
   │   • creates live embedding
   ├── Compare Embeddings
   │   • cosine distance
   ├── Find Smallest Distance
   │   • best match
   ├── Check threshold
   │   • if distance is < 0.30
   ├── Verify multiple matches
   │   • required matches = 5
   └── Mark Attendance
       • student_id + date + time + Present

3. Attendance Storage
   └── Save record in attendance.db
```

## Tools Used and Their Meaning

### Python
Main programming language for the entire project.

### Streamlit
Creates the web application interface where the user can register students and start attendance.

### OpenCV
Used for face detection in webcam frames.

### DeepFace
Provides face recognition features and helps convert face photos into embeddings.

### FaceNet512
The face model used to create unique face representations for comparison.

### SQLite
Local database used to store student records and attendance information.

### Pandas
Used for handling and displaying tabular data such as attendance and student lists.

### NumPy
Used for numerical calculations and embedding comparison.

### Pillow
Used for processing uploaded images.

### streamlit-webrtc
Used to access the webcam in the browser and stream live video into the app.

## How to Download the Project

```bash
git clone https://github.com/TeliMushera/FaceAttendAI.git
cd FaceAttendAI
```

## How to Run the Project

### 1. Create a virtual environment

```bash
python -m venv .venv
```

### 2. Activate the environment

Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Start the app

```bash
python -m streamlit run app.py
```

Then open the local URL shown in the terminal, usually:

```text
http://localhost:8501
```

## Project Structure

```text
FaceAttendAI/
├── app.py
├── requirements.txt
├── attendance.db
├── student_photos/
├── README.md
├── .gitignore
└── .python-version
```

## Important Notes

- Use a clear and front-facing photo for better recognition.
- Good lighting improves accuracy.
- Keep only one face in front of the camera for best results.
- This project stores data locally in SQLite for academic/demo use.

## Main Purpose

The main purpose of FaceAttend AI is to automate attendance using face recognition and make attendance marking faster, easier, and more accurate.