# MQTT Weather Station (WebSockets + SQLite)

This project is a weather station that retrieves temperature and humidity data from an MQTT broker via WebSockets, stores the data in an SQLite database, and visualizes it using Chart.js in a web interface.

## Features
- Real-time data collection via MQTT WebSockets
- Storage of sensor data in SQLite
- REST API to fetch the last 5 minutes of data
- Interactive chart visualization using Chart.js

## Prerequisites
Before running the project, ensure you have the following installed:
- Node.js (v14+ recommended)
- SQLite3
- An MQTT broker supporting WebSockets (e.g., Mosquitto)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Rukundo-Bahati/MQTT_Web_Sockets.git
cd MQTT_Web_Sockets
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure MQTT Broker
Ensure your MQTT broker supports WebSockets and is running on:
```
ws://157.173.101.159:9001
```
Modify `server.js` if needed to match your broker settings.

### 4. Run the Server
```bash
node server.js
```
The server will start at `http://localhost:3000`.

### 5. Open the Web Interface
Simply open `index.html` in a browser.
Alternatively, serve it using a simple HTTP server:
```bash
npx http-server
```

### 6. Verify Data Storage
You can check the stored data using SQLite CLI:
```bash
sqlite3 stored_data.db
SELECT * FROM sensor_data;
```

## API Endpoint
- **GET `/data`** → Fetches the last 5 minutes of temperature and humidity data.

## Troubleshooting
- Ensure your MQTT broker is running and accessible via WebSockets.
- If data isn't showing in the chart, check `console.log` for errors in `server.js` and the browser console.
- If the database is empty, confirm that messages are being received by the server (`Received: topic → value` logs should appear).

## License
This project is open-source and available under the MIT License.

