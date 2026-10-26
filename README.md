# Multimodal Attendance & Engagement Agent

A Streamlit-based attendance and classroom activity monitoring application.

## Features
- Manual attendance management
- Face detection and tracking using OpenCV
- Optional face recognition with enrolled student data
- Audio activity monitoring using microphone input
- Attendance and session analytics
- CSV reports and session summaries
- Rule-based teaching suggestions

## Technology Stack
- Python
- Streamlit
- OpenCV
- NumPy
- Pandas
- SQLite
- SoundDevice

## Installation
Install dependencies using:

    pip install -r requirements.txt

## Run the Application
    python -m streamlit run app.py

## Privacy and Limitations
Use face recognition only with appropriate consent. Audio intensity measures sound activity, not student attention. Teaching suggestions are rule-based and are not validated AI assessments.

## Execution
Designed for local execution with optional webcam and microphone input.
