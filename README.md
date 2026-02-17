Embedded ECG System using Raspberry Pi
Project Description

This project implements a real-time embedded electrocardiogram (ECG) measurement system based on a Raspberry Pi and an ADS1115 analog-to-digital converter.

The system acquires the electrical cardiac signal via electrodes, performs digital signal processing in real time, detects R-peaks, calculates heart rate (BPM), and visualizes the ECG signal using an SDL-based graphical interface.

⚠️ Disclaimer:
This system is developed for educational and research purposes only. It is not a certified medical device and must not be used for clinical diagnosis.

System Architecture

Signal flow:
Electrodes
→ Analog Front-End
→ ADS1115 (I2C ADC)
→ Raspberry Pi
→ Digital Filtering
→ R-Peak Detection
→ Heart Rate Calculation
→ SDL Visualization
→ CSV Data Logging

Main Features
Real-time ECG acquisition (200 Hz sampling rate)
Baseline correction (High-pass filter)
50 Hz power-line interference suppression (Notch filter)
Low-pass filtering
Moving Window Integration (MWI)
Adaptive R-peak detection (SPKI / NPKI method)
Robust BPM calculation with outlier reduction
Fullscreen SDL visualization (no desktop required)
Automatic CSV data recording

Hardware Requirements:
Raspberry Pi (tested on Raspberry Pi Zero)
ADS1115 16-bit ADC (I2C)
ECG analog front-end circuit
ECG electrodes
Stable power supply

Software Requirements:
Python 3
smbus2
PySDL2

Install dependencies:
pip3 install smbus2 pysdl2

Enable I2C on Raspberry Pi:
sudo raspi-config
Interface Options → I2C → Enable

Running the Program:
python3 Ekg-messung.py


The application runs in fullscreen mode using SDL and does not require a graphical desktop environment.

Keyboard Controls
Key	Function
P	Pause / Resume measurement
H	Toggle High-pass filter
N	Toggle Notch filter
L	Toggle Low-pass filter
R	Reset BPM calculation
Q	Quit program
Signal Processing Overview
Sampling

Sampling interval: 0.005 s
Effective sampling rate: 200 Hz

Filtering:
High-pass filter for baseline drift removal
50 Hz notch filter (biquad implementation)
First-order low-pass filter

R-Peak Detection:
Absolute value feature extraction
Moving Window Integration (MWI)
Adaptive threshold using signal and noise peak tracking
Refractory period control
Heart Rate Calculation
RR interval computation

Physiological range filtering:
Trimmed mean smoothing
Stable real-time BPM display

Data Logging:
ECG data are automatically stored as CSV files:
ekg_<subject>_<timestamp>.csv


File structure:
time_s,ekg_V

Educational Objectives
This project demonstrates:
Embedded medical signal acquisition

Real-time digital signal processing
Adaptive peak detection algorithms
Low-level graphical rendering using SDL
Performance considerations on resource-limited systems
