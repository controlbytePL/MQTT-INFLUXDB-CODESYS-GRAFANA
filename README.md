# Node-RED Flow: MQTT to InfluxDB with OEE Data Processing

## 📜 Overview
This Node-RED flow captures OEE metrics from an MQTT broker, processes the JSON payload, extracts individual variables, and logs them to InfluxDB.

## 🚀 Features
- Receives MQTT messages
- Parses and validates JSON payloads
- Processes OEE metrics
- Sends data to InfluxDB
- Provides debugging output for easy monitoring

## 🛠️ Requirements
- Node-RED installed
- InfluxDB (Version 1.x or 2.x)
- MQTT Broker (e.g., Mosquitto)

## 📥 Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/node-red-mqtt-influxdb.git
   ```
2. **Import the Flow into Node-RED:**
   - Go to Node-RED Dashboard
   - Click on Menu → Import → Paste the provided JSON
3. **Configure MQTT Broker and InfluxDB:**
   - Set your MQTT broker address and InfluxDB credentials in respective nodes.

## 📊 Flow Structure
1. **MQTT OEE Listener:** Receives all MQTT topics.
2. **Fix JSON Format:** Parses and cleans malformed JSON.
3. **Parse MQTT Payload:** Extracts numeric fields and structures payload for InfluxDB.
4. **Extract Variables:** Outputs OEE metrics individually.
5. **InfluxDB Out:** Stores structured data in the InfluxDB.
6. **Debug Node:** Displays output for verification.

## 📝 Example Payload
```json
{
  "OEE": 50,
  "Performance": 75,
  "Quality": 80,
  "Availability": 95,
  "MachineState": 1,
  "GoodParts": 100,
  "BadParts": 5,
  "ProductWeight": 5000
}
```

## 🖥️ Usage
- Start Node-RED and view logs via `http://localhost:1880`
- Check data in InfluxDB via Chronograf or CLI:
  ```bash
  influx -database 'mqtt_logs' -execute 'SELECT * FROM oee_data LIMIT 10'
  ```

## 📧 Support
If you encounter issues or need support, please raise an issue on GitHub.

## 📄 License
This project is licensed under the MIT License.
