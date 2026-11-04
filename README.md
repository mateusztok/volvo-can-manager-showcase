# Volvo CAN Controller & Diagnostic Manager

> **Showcase Repository / Case Study:**  
> This repository serves as an architectural case study and functional interface demonstration for portfolio purposes. The full firmware C++ source code is hosted in a private repository.

---

Custom diagnostic and control system developed specifically for Volvo vehicle, powered by the ESP32 microcontroller. Connected directly to the OBD-II port, the device interfaces with dual CAN buses (HS-CAN and LS-CAN), providing real-time engine telemetry, UDS/OBD-II diagnostics, audio warnings, and vehicle function automation.

---

## Features

* **DPF Monitoring:** Real-time tracking of soot mass, soot load, differential pressure, and DPF exhaust temperatures.
* **Engine Telemetry:** Live monitoring of Engine Speed, oil temperature, coolant temperature, EGR valve command, and battery voltage.
* **UDS / DTC Diagnostics:** Fault code readout from the ECM via UDS (ISO 14229 Service `0x19`) with readable fault descriptions and DTC clearing capability (OBD Mode 04).
* **Start-Stop Automation:** Smart control and automatic override of the vehicle's Start-Stop system over the LS-CAN bus based on engine operational state.
* **Audio Alert System (Buzzer):** Acoustic notifications for DPF regeneration state events and threshold safety breaches (e.g., critical coolant temperatures).
* **Wireless Web Dashboard:** Responsive web interface featuring low-latency data streaming via WebSockets.

---

## Interface Screenshots

<table width="100%">
  <thead>
    <tr>
      <th width="33%" align="center">Main Dashboard</th>
      <th width="33%" align="center">DTC Fault Diagnostics</th>
      <th width="33%" align="center">Fault Clearing</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><img src="https://github.com/user-attachments/assets/a32a2563-ad07-42e0-b16d-404d7b3e2cb8" width="100%" alt="Main Dashboard" /></td>
      <td align="center"><img src="https://github.com/user-attachments/assets/6b2f1aea-5cb5-4f6c-9326-09799ec24176" width="100%" alt="DTC Fault Diagnostics" /></td>
      <td align="center"><img src="https://github.com/user-attachments/assets/b6cbe85f-cdab-4609-97b4-623a07dbad90" width="100%" alt="Fault Clearing" /></td>
    </tr>
  </tbody>
</table>
---





## Hardware & Tech Stack

* **Environment:** Native ESP-IDF (C++17, FreeRTOS).
* **Hardware Layer:**
  * ESP32 Microcontroller.
  * External HS-CAN Transceiver SN65HVD230.
  * External MCP2515 CAN Module via SPI (handling LS-CAN).
  * Piezo Buzzer audio alert module.
* **Diagnostic Protocols:** UDS (ISO 14229-1), CAN-TP / DoCAN (ISO 15765-2), OBD-II (Mode 01, Mode 04).
* **User Interface:** HTML5, CSS3, JavaScript (WebSockets, mDNS).
