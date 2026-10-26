# Multimodal Attendance & Engagement Agent — Working Prototype

## Features
- Manual attendance with same-day duplicate prevention.
- SQLite persistence; creates missing tables with `CREATE TABLE IF NOT EXISTS` and does not delete existing attendance records.
- Consent-based face sample enrollment stored locally under `face_data/`.
- Optional LBPH face recognition using OpenCV-contrib. Predictions are probabilistic and must be verified by a person.
- Webcam face detection, temporary presence tracking, session reports and CSV exports.
- Optional microphone RMS sound-level sample; raw audio is not saved.
- Attendance analytics, charts, recognition logs and rule-based teacher-support suggestions.

## Windows setup
Run these commands in PowerShell from the project folder:

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Open `http://localhost:8501`.

If `.venv` already exists, do not recreate it; just install requirements and run Streamlit.

## Database safety
- The app expects `attendance.db` in the same folder as `app.py`.
- The ZIP intentionally does not include any database file.
- Back up the existing database before replacing `app.py`.
- The app adds missing tables without deleting existing tables/records.

## Face recognition enrollment
1. Ensure students have been informed and have consented to local face-sample capture.
2. Open **Face Enrollment**, enter name and student ID, confirm consent, and capture samples in good lighting.
3. Repeat enrollment for each student.
4. Open **Recognition & Tracking** and test with one enrolled student at a time.
5. Review results manually. LBPH distance is not a calibrated probability. Poor lighting, pose, camera and look-alikes can cause errors.

## Honest limitations
This is a college/demo prototype, not a validated production system. Face recognition can be wrong and should not be the sole basis for official attendance. The audio feature measures amplitude only; it does not transcribe speech, identify speakers, detect emotion, or prove attention. Face counts and audio levels do not measure learning or engagement. Suggestions are rule-based heuristics, not trained AI. Obtain appropriate consent and follow your institution's data policy. Face samples are stored in `face_data/`; protect or delete them when no longer needed.
