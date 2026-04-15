# SmartPlant

SmartPlant is a smart irrigation system for paddy fields that combines ESP32 hardware, a Flask backend, and a web dashboard to monitor soil conditions and support irrigation decisions.

## Live App

- live link: https://smart-plant-r0me.onrender.com

## Features

- Real-time soil moisture and climate monitoring
- Irrigation prediction using machine learning
- Manual pump control from the web dashboard
- Multi-zone support for different field sections
- Browser notifications for alerts and updates
- PWA support for mobile-style access

## How It Works

1. The ESP32 reads sensor data such as soil moisture, temperature, and humidity.
2. The backend stores the data, runs irrigation logic, and serves API responses to the frontend.
3. The frontend shows live values, alerts, and controls so the user can monitor and manage irrigation from the browser.

## Hardware

- ESP32-based controller
- Soil moisture, temperature, and humidity sensors
- Relay or pump control for irrigation
- Hardware guide and firmware files are in `backend/hardware/`

## Tech Stack

- Backend: Flask, SQLite, Pandas, scikit-learn
- Frontend: HTML, CSS, JavaScript, Tailwind CSS
- Hardware: ESP32 + sensors + relay/pump

## Run Locally

### Backend

```bash
cd backend
pip install -r requirements.txt
python app.py
```

When you run it on your own computer, the backend usually opens at `http://localhost:5000`.

When the project is deployed, the app uses the live Render backend instead of localhost.

The frontend is a static web app, so it can be opened directly in a browser or served with any static file server.

### Frontend

Open `frontend/index.html` in your browser, or serve the `frontend` folder with any static server.

## Deployment Notes

### Backend on Render

- Use [render.yaml](render.yaml) for the backend service.
- Set the required Render environment variables.

### Frontend on Render

Users should open the frontend live link above. If your backend URL changes, update the API base in [frontend/index.html](frontend/index.html).

## Notes

- SQLite is used for local storage.
- Push notifications need valid VAPID keys.
- The frontend talks to the deployed backend over HTTPS.
