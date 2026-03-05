Parkinson’s Disease Monitoring System
1. Overview

This project presents a wearable monitoring system designed to assist in the observation of symptoms related to Parkinson’s Disease. The system focuses on detecting tremors, monitoring physical activity, and identifying potential fall events using motion sensing and signal processing techniques.

The device continuously collects motion data from a sensor and processes it in real time to detect abnormal patterns. When significant tremor activity or a fall is detected, the system sends alerts through an IoT platform so caregivers or medical personnel can respond quickly.

The goal of this project is to provide a low-cost and accessible monitoring solution that can improve patient safety and assist in early intervention during emergencies.

2. Objective

To monitor motion patterns associated with Parkinson’s Disease using a wearable system.

To detect tremors using signal processing techniques.

To identify potential fall events using acceleration thresholds.

To send real-time alerts through an IoT platform.

To provide continuous remote monitoring for caregivers and healthcare professionals.

3. Key Features

Real-time tremor monitoring using motion sensors.

Fast Fourier Transform (FFT) based frequency analysis for tremor detection.

Fall detection using acceleration magnitude thresholds.

Activity classification such as rest, walking, and tremor states.

Real-time IoT monitoring through the Blynk platform.

Emergency alerts for abnormal movement or fall events.

4. Hardware Components

ESP32 Microcontroller

MPU6050 Accelerometer and Gyroscope Sensor

Buzzer for alert indication

WiFi connectivity module (integrated with ESP32)

Power supply

5. Software and Technologies

Arduino IDE for firmware development

Embedded C/C++ programming

Blynk IoT platform for remote monitoring

Signal processing using Fast Fourier Transform (FFT)

6. Working Principle
6.1 Motion Data Collection

The MPU6050 sensor continuously measures acceleration and angular velocity in three axes. These signals represent the movement patterns of the user.

6.2 Tremor Detection

Parkinsonian tremors typically occur in a specific frequency range. The system uses a Fast Fourier Transform (FFT) algorithm to convert the time-domain motion signal into the frequency domain. By analyzing dominant frequency components, tremor activity can be detected.

6.3 Activity Monitoring

Movement magnitude is analyzed to classify user states such as resting, walking, or tremor activity.

6.4 Fall Detection

If the acceleration magnitude suddenly exceeds a predefined threshold followed by inactivity, the system interprets it as a possible fall event.

6.5 Alert System

When tremor intensity crosses a threshold or a fall is detected, the system sends notifications through the Blynk platform and activates a buzzer.

7. Implementation

The ESP32 collects real-time motion data from the MPU6050 sensor.

Data is processed to calculate acceleration magnitude.

FFT is applied to analyze frequency components of motion signals.

Threshold algorithms determine tremor activity and fall events.

Detected events are transmitted through WiFi to the Blynk IoT platform.

Alerts and monitoring data are displayed on a mobile dashboard.

8. Applications

Parkinson’s Disease patient monitoring

Elderly fall detection systems

Remote healthcare monitoring

Smart wearable health devices

9. Future Improvements

Integration with machine learning models for more accurate detection.

Development of a compact wearable form factor.

Mobile application for real-time health analytics.

Integration with hospital monitoring systems.

10. Achievement

This project was presented in a technical competition and secured 3rd Prize, competing against projects developed over much longer periods. The project demonstrates how embedded systems and signal processing can be combined to create practical healthcare solutions.
