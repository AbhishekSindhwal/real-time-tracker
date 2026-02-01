# Real-Time Location Tracker 📍

A simple real-time location tracking web application built using **Node.js**, **Express**, **Socket.IO**, and **Leaflet.js**.  
The application allows multiple users to share their live location and view each other’s position on an interactive map in real time.

---

## 🚀 Features

- Real-time location sharing using WebSockets
- Live map updates without page refresh
- Multiple users tracking simultaneously
- Automatic marker update when user moves
- Marker removal when a user disconnects
- Mobile GPS support (best accuracy over HTTPS)
- Lightweight and easy to understand architecture

---

## 🛠️ Tech Stack

- **Backend:** Node.js, Express.js
- **Real-Time Communication:** Socket.IO
- **Frontend:** EJS, JavaScript
- **Maps:** Leaflet.js with OpenStreetMap
- **Geolocation:** Browser Geolocation API


---

## ⚙️ How It Works

1. When a user opens the application, the browser asks for **location permission**.
2. The browser continuously tracks the user’s latitude and longitude using the **Geolocation API**.
3. The client sends location updates to the server using Socket.IO (`send-location` event).
4. The server broadcasts the location to all connected clients (`receive-location` event).
5. Each client updates or creates a marker on the map for that user.
6. When a user disconnects, their marker is removed from the map in real time.

---

## 🧠 Backend Logic Overview

- An HTTP server is created using Express.
- Socket.IO is attached to the HTTP server.
- Each connected client is assigned a unique `socket.id`.
- Location data is broadcasted to all clients along with the sender’s socket ID.
- On disconnection, all clients are notified to remove the corresponding marker.

---

## ▶️ How to Run Locally
```bash
git clone https://github.com/AbhishekSindhwal/real-time-tracker.git
cd real-time-tracker
npm install
node index.js






