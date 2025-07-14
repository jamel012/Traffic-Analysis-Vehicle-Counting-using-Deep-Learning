## 🚗 Traffic Analysis & Vehicle Counting System
This repository contains a vehicle detection, tracking, and traffic analysis system developed using both deep learning and classical machine learning techniques.

It was built as part of a team project for the College of Computer Science and Engineering at the University of Jeddah, Kingdom of Saudi Arabia.

The goal of this project is to analyze traffic flow, classify traffic conditions, and predict congestion trends to support better transportation planning and infrastructure development.

## 🚀 Features
The system combines:

✅ Deep Learning

YOLOv8 for real-time vehicle detection in video streams

DeepSORT for robust vehicle tracking across video frames

✅ Machine Learning

Random Forest (RF) for classifying traffic situations (low/normal/high/heavy)

Gaussian Mixture Model (GMM) for discovering traffic patterns and labeling unseen data

✅ Data Export

CSV logging of:

Timestamps

Date and day of the week

Vehicle counts (car, bus, truck, motorcycle)

Average vehicle exit time

Road status (main or secondary)

Traffic situation classification

This pipeline enables both real-time monitoring and long-term analysis of traffic patterns.

## 🎥 How It Works
YOLOv8 detects vehicles in each frame of the video.

DeepSORT assigns a unique ID to each vehicle and tracks it across frames.

A Virtual Detection Zone (VDZ) is drawn horizontally across the frame:

Vehicles crossing this line are counted.

For every minute:

Vehicle counts are logged.

The traffic situation is classified using machine learning models.

## 📊 Example CSV Output
time	date	day_of_week	car_count	motorcycle_count	truck_count	bus_count	total	avg_exit_time_seconds	road_status	traffic_situation
16:31:00	2025-04-21	Monday	10	1	2	0	13	2.5	m	high


## 💻 Usage
✅ Important:
Place your traffic video in:

bash
Copy
Edit
data/raw/
Then run:

bash
Copy
Edit
python src/main.py
You will be prompted to enter:

Road status → main (m) or secondary (s)

The pipeline will:

Process the video

Log vehicle counts into a CSV file under:

bash
Copy
Edit
data/output_csv/
## ⚙️ Configuration
Adjust project settings in src/config.py:

python
Copy
Edit
CSV_PATH = "data/output_csv/vehicle_counts.csv"
VIDEO_PATH = "data/raw/your_video.mp4"
SHOW_DEBUG = True
USE_ROI = True
CROP_TOP = 400
CROP_BOTTOM = 0
CROP_LEFT = 50
CROP_RIGHT = 0
VDZ_POSITION = 0.18
START_TIME_STR = '2025-04-21 16:31:00'
SITUATION_ALL = ['3','2','2','2','2','2']
SHOW_DEBUG → Display frames with bounding boxes and IDs

ROI cropping → Trim video borders

VDZ_POSITION → Location of virtual counting line

## 📈 Jupyter Notebooks
Exploratory analysis and experiments can be found in:

bash
Copy
Edit
notebooks/exploration.ipynb
## 📄 Project Report
The final project report is available in:

Copy
Edit
reports/Final_progress_report.pdf
## 👥 Authors
This project was developed as a team project for:

CCCS323 Machine Learning – University of Jeddah, KSA
Team Number: 3

Team Members:

[Your Name]

[Teammate 2 Name]

[Teammate 3 Name]
