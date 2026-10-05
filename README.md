# FaceAttend AI

FaceAttend AI is a face-recognition based attendance management system
that uses computer vision and deep learning to identify registered students
through a webcam and record their attendance automatically.

## Features

- Student registration
- Student photo management
- Face recognition
- Live webcam attendance
- Automatic attendance recording
- Student directory
- Edit and delete student details
- Attendance records
- SQLite database
- Streamlit web interface


## Technologies Used

- Python
- Streamlit
- OpenCV
- DeepFace
- FaceNet512
- SQLite
- Pandas
- NumPy
- streamlit-webrtc


## Installation

### 1. Clone the repository

git clone <your-github-repository-url>

### 2. Open the project folder

cd FaceAttendAI

### 3. Create a virtual environment

python -m venv .venv

### 4. Activate the environment

Windows:

.venv\Scripts\activate

### 5. Install dependencies

pip install -r requirements.txt

### 6. Run the application

python -m streamlit run app.py