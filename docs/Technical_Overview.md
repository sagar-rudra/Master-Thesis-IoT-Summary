# Technical Overview – ESP32-Based Wearable IoT Device

## 1. System Architecture
The system consists of an ESP32-WROVER-IE microcontroller connected to two sensors
(DS18B20 temperature sensor and MAX30102 oximetry sensor) and an external knitted
textile antenna via a 50 Ω u.FL–to–SMA connector.

The ESP32 acts as:
- Data acquisition unit
- Wireless communication unit (Bluetooth & Wi-Fi)
- Test platform for evaluating textile antenna performance

---

## 2. Hardware Configuration

### 2.1 Microcontroller
- ESP32-WROVER-IE
- Integrated Bluetooth Classic, BLE, and Wi-Fi
- External antenna interface (u.FL connector)

### 2.2 Sensors
- DS18B20: Digital temperature sensor (OneWire protocol)
- MAX30102: Infrared oximetry sensor (I²C protocol)

Pull-up resistors (4.7 kΩ) were used on all data lines to ensure stable communication.

---

## 3. Wireless Communication Modes

### 3.1 Bluetooth Mode
- ESP32 configured as a Bluetooth Serial device
- Sensor values are transmitted every second
- Data visualized using an Android Bluetooth terminal application

### 3.2 Wi-Fi Mode
- ESP32 configured as a local web server
- Sensor data displayed on a dynamically refreshed HTML webpage
- Real-time access via smartphone browser

---

## 4. Textile Antenna Integration
A knitted dipole antenna fabricated on a textile substrate was connected directly
to the ESP32 RF port. All wireless transmission during testing was performed
exclusively using the textile antenna.

Key challenges observed:
- Resonance frequency shift due to textile dielectric properties
- Sensitivity to fabrication tolerances and environmental conditions

---

## 5. RF Measurement and Evaluation
A Vector Network Analyzer (VNA) was used to characterize antenna performance.

Measured parameters:
- Return Loss (S11)
- Standing Wave Ratio (SWR)

Results showed:
- Strong resonance near 0.64 GHz with good impedance matching
- Detuning from the intended 2.4 GHz ISM band
- Successful wireless data transmission despite detuning

---

## 6. Key Engineering Challenges
- Antenna detuning due to textile material and body proximity
- Sensor initialization and library conflicts
- Stable Wi-Fi reconnection handling
- Power and signal stability during long test runs

---

## 7. Scope and Limitations
- The full thesis document is not publicly shared
- Complete firmware source code is not included
- Repository is intended as a technical portfolio overview

