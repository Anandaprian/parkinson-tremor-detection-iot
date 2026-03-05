Parkinson's Disease Tremor & Fall Monitoring System

An IoT-based wearable monitoring system designed to assist patients with Parkinson's disease through real-time tremor detection and fall detection using embedded signal processing and cloud connectivity.

This project uses an ESP32 microcontroller, MPU6050 motion sensor, FFT signal analysis, and Blynk IoT platform to continuously monitor patient movement and provide instant alerts for abnormal tremors or fall events.

🏆 3rd Prize Winner – Engineering Project Competition

Project Overview

Parkinson’s disease affects millions of people worldwide and often causes:

Resting tremors

Postural instability

High risk of falls

Difficulty in continuous symptom monitoring

Traditional clinical evaluations occur only during hospital visits and cannot capture daily symptom fluctuations.

This system provides continuous monitoring, allowing tremor patterns and fall events to be detected in real time.

Key Features
Real-Time Tremor Detection

Uses Fast Fourier Transform (FFT) to analyze gyroscope motion data and detect tremor frequencies typical in Parkinson’s disease.

Typical Parkinson's tremor frequency:

4 – 6 Hz

The system detects tremor energy in the range:

3.5 – 7 Hz

Fall Detection System

A multi-stage algorithm detects falls using:

Free fall detection

Impact detection

Gyroscope validation

Confirmation timer

This reduces false positives and improves reliability.

IoT Cloud Monitoring

Using the Blynk IoT platform, the system can:

Send fall alerts instantly

Display tremor status remotely

Provide real-time monitoring through a mobile dashboard

Local Patient Feedback

The wearable device includes:

OLED display showing system status

Buzzer alert for fall detection

Continuous monitoring indicators

System Architecture

Hardware Components:

ESP32 Microcontroller

MPU6050 6-axis IMU Sensor

128×64 OLED Display

Buzzer Alert System

WiFi Connectivity

Software Components:

Arduino Framework

ArduinoFFT Library

Blynk IoT Platform

Embedded Signal Processing Algorithms

Tremor Detection Algorithm

The system uses Fast Fourier Transform (FFT) to convert motion data from the time domain to the frequency domain.

Steps:

Gyroscope data sampled at 100 Hz

64 samples collected for analysis

Hamming window applied to reduce spectral leakage

FFT computed to obtain frequency spectrum

Energy calculated within 3.5 – 7 Hz tremor band

If the energy exceeds a threshold, tremor is detected.

Fall Detection Logic

Fall detection uses a state machine approach:

States:

IDLE → FREE_FALL → IMPACT → CONFIRM → FALL_CONFIRMED

Detection thresholds:

Free-fall threshold
< 0.35 g

Impact threshold

2.5 g

Gyroscope threshold

120°/s

Confirmation window
3 seconds

If confirmed, the system:

Activates buzzer alert

Sends notification to Blynk cloud

Displays fall status on OLED

Data Processing Pipeline
Task	Interval
MPU Sensor Sampling	10 ms
Fall Detection Check	20 ms
FFT Tremor Analysis	200 ms
Display & Cloud Update	500 ms
Files in Repository

tremor.txt

Main program implementing:

Tremor detection using FFT

fake Fall detection dummy code for the stable tremor detection.

OLED display updates

Blynk cloud communication

fall.txt

Simplified fall detection algorithm used for testing fall detection logic independently.

Hardware Wiring

MPU6050 → ESP32

SDA → GPIO 21
SCL → GPIO 22

OLED Display

SDA → GPIO 21
SCL → GPIO 22

Buzzer

Signal → GPIO 4

Applications

Parkinson's disease monitoring

Elderly fall detection systems

Remote healthcare monitoring

Wearable medical devices

Smart rehabilitation systems

Future Improvements

Machine learning based tremor classification

Mobile application with historical tremor graphs

Battery powered wearable prototype

Multi-patient cloud dashboard for hospitals

Author

Developed as a personal embedded systems project exploring:

Biomedical sensing

Signal processing

IoT healthcare systems

Real-time embedded programming