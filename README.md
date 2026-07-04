# Self-Hosted Temperature Logging Stack (Ubidot Alternative)

A custom, subscription-free Internet of Things (IoT) server architecture built on **Oracle Cloud (Always Free Tier)** to log real-time temperature telemetry from multiple **ESP32** sensor nodes deployed inside a academic laboratory.

## System Architecture

```text
 [ ESP32 Node ] ──(lab network / Outbound Port 80 HTTP)──> [ Oracle Cloud Server ]
                                                                │
                                                 ┌──────────────┴──────────────┐
                                                 ▼                             ▼
                                          [ Mosquitto ]                   [ Node-RED ]
                                                 │                             │
                                                 ▼                             ▼
                                           [ InfluxDB ]                 [ Telegram App ]
                                                 │                       (Alerts Engine)
                                                 ▼
                                            [ Grafana ]
                                        (Dashboard Display)
```

## Features

* **Enterprise Network Compatibility:** Seamlessly authenticates and operates within strict WPA2-Enterprise networks.
* **Firewall Bypass:** Operates ingestion channels over Port 80, evading outbound network port blocking.
* **Relational Alerts Engine:** Real-time upper/lower threshold event testing via Node-RED with instantaneous mobile push routing via Telegram API.
* **Time-Series Engine:** Continuous logging with InfluxDB optimization, built for rapid retrieval over long periods.
* **Stunning UI Analytics:** Modular live gauge tracking and trend lines built via Grafana.

## Technologies Used

* **Hardware:** ESP32, DS18B20 High-Precision Temperature Sensors.
* **Infrastructure:** Oracle Cloud VM (Always Free Tier), Ubuntu Server.
* **Deployment:** Docker, Docker-Compose.
* **Telemetry Processing:** Eclipse Mosquitto (MQTT), Node-RED.
* **Analytics & Storage:** InfluxDB, Grafana.