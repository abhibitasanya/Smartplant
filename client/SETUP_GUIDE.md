# SmartPlant Setup Guide

This single guide combines web deployment and Android app packaging.

## Section 1: Public Web Deployment

### Server (Render)

1. Create a Render web service with root directory set to `server`.
2. Build command:

```bash
pip install -r requirements.txt
```

3. Start command:

```bash
python app.py
```

4. Add environment variables:
- `SMARTPLANT_JWT_SECRET` = strong random value
- `SMARTPLANT_ESP_DEVICE_KEY` = strong key for ESP devices

5. After deploy, copy your server URL like:
- `https://smartplant-api.onrender.com`

### Client (Netlify)

1. Deploy the `client` folder on Netlify.
2. This project publishes from the `client` folder (configured in `netlify.toml`).
3. Open your site URL and use **Set API URL** on login page.
4. Paste your Render backend URL and save.

### Install As Phone App (PWA)

1. Open the public client URL on phone.
2. Use **Add to Home Screen** / **Install App**.
3. SmartPlant works like an installed app.

## Section 2: Android APK Build (Capacitor)

### Prerequisites

- Node.js LTS
- Android Studio + Android SDK
- Java 17

### Commands

```bash
cd client
npm install
npm run cap:add:android
npm run cap:sync
npm run cap:open:android
```

In Android Studio:
- Build > Build Bundle(s)/APK(s) > Build APK(s)

### API URL Note

- For phone testing, server URL should not be `127.0.0.1`.
- Use your public server URL or local LAN IP if testing on the same WiFi.

## Section 3: Train ML Model (Optional)

Training is now built into the server entry file.

```bash
cd server
python app.py --train-model
```

This reads `irrigation_prediction.csv` and updates `model.pkl`.
