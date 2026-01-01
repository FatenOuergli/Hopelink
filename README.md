demo_v2 includes a demonstration of the whole Platform! Enjoy



#Patient Therapeutic Monitoring Platform

Developed under the supervision of the MARS Laboratory (ISITCom), specifically the Smart Data Mining (SDM) team.

This project is a web-based platform for real-time monitoring and management of patients’ therapeutic programs, integrating AI, IoT, and a secure web interface.

#Project Structure Overview

project-root/

│

├── api/ # Backend (Django, JWT, MQTT, AI integration)

├── site/ # Frontend (Next.js, TailwindCSS, real-time display)

├── ai/ # AI model training and synthetic dataset generation

└── arduino_iot/ # Arduino code for M5StickC Plus2 (IoT device)

#Backend – api/

The api/ folder contains the entire backend, built using Django (Python). It features secure authentication with:

CSRF protection (Cross Site Request Forgery)

JWT tokens (JSON Web Tokens for user session validation)

Key Components:

Models: Classes such as Doctor, Patient, User, ActivityType, etc., represent core entities.

services.py: Manages interactions and relationships between backend models (acting as a service layer).

views.py (in each Django app declared in settings.py): Handles HTTP requests, exposes RESTful APIs for frontend interaction.

Integration:

AI integration: Loads the trained model from the ai/ folder to run predictions in the backend.

IoT support: Includes an MQTT broker connection to receive real-time physiological data from an M5StickC Plus2 device.

Database: Uses PostgreSQL as the main database (though sqlite might be used locally for development/testing).

#Frontend – site/

The site/ folder includes the full user interface of the platform, built using:

Next.js (React framework for server-side rendering and routing)

TailwindCSS (utility-first CSS framework for responsive design)

JSX (JavaScript XML syntax used in React components)

WebSockets: Enables real-time data visualization by subscribing to backend updates.

The frontend fetches data from the backend APIs and dynamically renders patient insights and device metrics.

#Artificial Intelligence – ai/

The ai/ folder includes:

Model training scripts developed using Google Colab

Scripts for synthetic dataset generation, simulating physiological metrics for testing/training

The resulting model is compressed and integrated into the Django backend to enhance decision-making.

#Internet of Things (IoT) – arduino_iot/

This directory includes the core Arduino IDE code that configures the M5StickC Plus2 device to:

Display Real-Time Clock (RTC)

Show battery percentage (BAT) and heart rate (HR)

Transmit physiological data in real-time using MQTT

IoT Architecture:

MQTT Protocol: Lightweight publish-subscribe messaging protocol

Mosquitto MQTT Broker: Used locally to bridge and relay data

MQTT Explorer: Used as a client to subscribe to real-time data and validate the transmission

The device publishes data via MQTT, which is then stored and processed by the backend and visualized on the frontend.

#Summary This project demonstrates the interdisciplinary integration of:

#AI for intelligent monitoring

#IoT for real-time physiological tracking

#Web technologies for user-friendly visualization

#Secure backend with modern protocols (JWT, CSRF)

#Research-grade data processing and smart medical support
