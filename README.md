# SmartPlant

<p align="center">
  SmartPlant is a smart irrigation platform for paddy fields, combining ESP32 hardware, a Flask backend, and a web dashboard for real-time monitoring and pump control.
</p>

<p align="center">
  <a href="https://smart-plant-r0me.onrender.com">
    <img src="https://img.shields.io/badge/LIVE%20DEMO-0F766E?style=for-the-badge&logo=render&logoColor=white" alt="Live Demo" />
  </a>
</p>

<p align="center">
  <a href="frontend/SETUP_GUIDE.md">
    <img src="https://img.shields.io/badge/Frontend%20Setup-1D4ED8?style=for-the-badge&logo=readthedocs&logoColor=white" alt="Frontend Setup" />
  </a>
  <a href="backend/hardware/HARDWARE_GUIDE.md">
    <img src="https://img.shields.io/badge/Hardware%20Guide-92400E?style=for-the-badge&logo=arduino&logoColor=white" alt="Hardware Guide" />
  </a>
</p>

## Overview

SmartPlant helps growers monitor soil moisture, temperature, humidity, and irrigation status from a single dashboard. Sensor readings are collected by the ESP32, processed by the backend, and displayed in the web interface for quick action.

## Features

- Real-time field monitoring
- Irrigation prediction with machine learning
- Manual pump control from the dashboard
- Browser notifications for alerts
- PWA support for mobile-style access

## How It Works

1. The ESP32 reads sensor data from the field and sends it to the backend API.
2. The backend stores the readings, applies irrigation logic, and serves app data.
3. The dashboard shows live values, alerts, and controls for monitoring and action.

## Tech Stack

- Backend: Flask, SQLite, Pandas, scikit-learn, JWT, Web Push
- Frontend: HTML, CSS, JavaScript, Tailwind CSS, PWA
- Hardware: ESP32, soil moisture sensor, DHT sensor, relay / pump

## Quick Start

### Backend

```bash
cd backend
pip install -r requirements.txt
python app.py
```

The backend runs locally at `http://localhost:5000` during development.

### Frontend

Open `frontend/index.html` in your browser or serve the `frontend` folder with any static file server.

### Hardware

Use `Smart_Plant.ino` or the hardware guide in `backend/hardware/` to connect the ESP32, sensors, and relay.

## Deployment

- Use [render.yaml](render.yaml) for the backend service on Render.
- Set the required environment variables for JWT, ESP device access, and VAPID push keys.
- If the backend URL changes, update the API base in [frontend/index.html](frontend/index.html).

## Documentation

- [Frontend setup guide](frontend/SETUP_GUIDE.md)
- [Hardware integration guide](backend/hardware/HARDWARE_GUIDE.md)

## Notes

- SQLite is used for local storage.
- Push notifications require valid VAPID keys.
- Production communication should use HTTPS.
