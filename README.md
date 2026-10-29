# Footstep-Based Power Generation with Integrated Crowd Density Monitoring and Stampede Alert System

## 📌 Project Overview

This project combines **piezoelectric energy harvesting, embedded systems, and Internet of Things (IoT)** to demonstrate footstep-based power generation and real-time crowd activity monitoring.

Piezoelectric sensors generate electrical voltage when mechanical pressure is applied by footsteps. An ESP32 microcontroller processes the sensor signals, counts footsteps, and communicates data to the Blynk IoT platform. When the detected footstep activity exceeds a predefined threshold, the system triggers a crowd alert and sends a notification through the IoT platform.

The project aims to support sustainable energy utilization and improve crowd safety in high-footfall public places.

## 🎯 Objectives

- Generate electrical energy from human footsteps using piezoelectric sensors.
- Convert the generated AC voltage into DC using a bridge rectifier.
- Monitor footstep activity in real time using an ESP32.
- Detect unusually rapid footstep activity using threshold-based logic.
- Display sensor readings and footstep counts through Blynk IoT.
- Generate alerts when abnormal footstep activity is detected.
- Explore applications in smart cities and public safety systems.

## 🛠️ Hardware Components

| Component | Purpose |
|---|---|
| ESP32 Microcontroller | Processes sensor data and provides Wi-Fi connectivity |
| Piezoelectric Discs | Generate voltage in response to mechanical pressure |
| Bridge Rectifier | Converts AC output into DC |
| Filter Capacitors | Smooth the rectified voltage |
| Rechargeable Battery / Power Bank | Provides a stable power supply |
| Resistors | Limit current and protect circuit components |
| LED | Provides visual indication of system status |
| Breadboard and Connecting Wires | Enable circuit assembly and connections |

## 💻 Software and Technologies

- **Arduino IDE** — Microcontroller programming
- **Embedded C/C++** — ESP32 firmware development
- **Blynk IoT** — Real-time monitoring and alert notifications
- **Wi-Fi Communication** — Transfers sensor data to the cloud
- **ESP32 ADC** — Reads analog signals from the piezoelectric sensor

## ⚙️ Working Principle

### 1. Footstep-Based Energy Generation

When a person steps on a piezoelectric disc, mechanical stress produces an electrical voltage through the piezoelectric effect.

The generated output is rectified, filtered, and conditioned to obtain DC voltage. The processed energy can be stored and used for low-power electronic applications, subject to the amount of energy harvested and the efficiency of the power-conditioning circuit.

### 2. Footstep Detection

The ESP32 reads the analog output of the piezoelectric sensor.

The system uses threshold-based detection to identify footsteps. When the sensor value exceeds the predefined threshold, a footstep is registered.

A lockout interval prevents repeated counts caused by sensor vibrations following a single step.

### 3. Crowd Activity Monitoring

The system counts detected footsteps within a fixed time window of five seconds.

In the implemented logic, more than five footsteps within this window trigger a crowd alert. The threshold is configurable and should be calibrated according to the installation environment.

This approach detects rapid footstep activity as a possible indicator of unusual crowd movement. It does not independently measure the actual number of people or reliably establish stampede conditions.

### 4. IoT Monitoring and Alerts

The ESP32 connects to the Blynk IoT platform over Wi-Fi and transmits sensor readings, cumulative footstep counts, and alert status.

The Blynk dashboard displays the incoming data. When the configured alert condition is met, the system activates the alert indicator and can send a push notification through the Blynk platform.

## 🔄 System Workflow

```text
Human Footstep
      |
      v
Piezoelectric Sensor
      |
      +--------------------------+
      |                          |
      v                          v
Voltage Generation         Sensor Signal
      |                          |
      v                          v
Bridge Rectifier             ESP32
      |                          |
      v                          v
Filtering and             Footstep Detection
Power Conditioning              |
      |                          v
      v                    Step Counting
Energy Storage                  |
      |                          v
Low-Power Applications    Five-Second Window
                                 |
                                 v
                       Threshold Evaluation
                                 |
                                 v
                          Crowd Alert
                                 |
                                 v
                           Blynk IoT
                                 |
                                 v
                      Remote Monitoring
                      and Notifications
```

*Note: The energy-harvesting path and the monitoring path are shown separately for clarity. The actual power supply and energy-storage connections must match the implemented hardware.*

## 📊 Results

The prototype demonstrates the following functions:

- Detection and counting of footsteps using piezoelectric sensor signals.
- Transmission of sensor readings to the Blynk IoT dashboard.
- Real-time visualization of footstep activity.
- Generation of an alert when the configured footstep threshold is exceeded.
- Demonstration of the potential integration of energy harvesting and IoT-based safety monitoring.

Quantitative power-generation efficiency, detection accuracy, and false-alarm rates require separate measurements and validation.

## ✅ Advantages

- Utilizes mechanical energy available from human movement.
- Provides real-time monitoring of footstep activity.
- Supports remote monitoring through an IoT dashboard.
- Uses a modular and relatively simple hardware architecture.
- Can be adapted for further experimentation in crowd monitoring and smart infrastructure.

## ⚠️ Limitations

- Piezoelectric energy output is relatively low and depends on applied force, sensor arrangement, and mechanical coupling.
- Footstep counts alone cannot determine actual crowd density or confirm a stampede.
- Fixed thresholds may produce false alerts in environments with different walking patterns.
- Sensor placement and floor construction affect detection performance.
- Continuous operation may require a rechargeable battery or an external power source when harvested energy is insufficient.
- Reliable deployment requires extensive testing under realistic crowd conditions.

## 🚀 Future Scope

- Deploy multiple sensor nodes for spatial crowd activity monitoring.
- Incorporate dedicated crowd-density sensors, such as infrared sensors or camera-based systems.
- Develop more advanced algorithms to identify abnormal movement patterns.
- Improve energy harvesting, voltage regulation, and energy storage.
- Integrate GSM or LoRa communication for applications with limited Wi-Fi coverage.
- Connect the alert system to emergency lighting, public-address systems, and digital display boards.
- Collect experimental data to evaluate detection accuracy, energy output, and system reliability.

## 🏙️ Applications

- Railway stations and metro platforms
- Stadiums and concert venues
- Religious gatherings and public events
- Shopping malls and exhibition centres
- Smart-city infrastructure
- High-footfall pedestrian areas

## 👥 Project Team

- Kasif Nawaz — 23BEE050
- Saheb Anees — 23BEE056
- Tausif Raza — 23BEE059
- Waris Khan — 23BEE061
- Zartasha Nasir — 23BEE062

## 📚 References

1. S. Priya and D. J. Inman, *Energy Harvesting Technologies*. Springer, 2009.
2. A. Khalid et al., “Piezoelectric energy harvesting systems: A review,” *Sensors*, vol. 18, no. 3, 2018.
3. Espressif Systems, *ESP32 Technical Reference Manual*, 2022.
4. Blynk Inc., *Blynk IoT Platform Documentation*.
5. N. K. Suryadevara and S. C. Mukhopadhyay, “Wireless sensor network based smart monitoring of public environments,” *IEEE Sensors Journal*, vol. 15.

---

**Disclaimer:** This project is an academic prototype intended to demonstrate energy harvesting and footstep-based crowd activity alerts. It is not a certified stampede prediction or public-safety system.
