# Arduino Based PC Controlled Buzzer
# 🔔 Premium Buzzer Controller (Arduino + PyQt5)

A **desktop GUI application** built with **Python (PyQt5)** that allows you to **control an Arduino-connected buzzer** using a modern, premium-style interface.  
With a single click, you can turn the buzzer **ON** or **OFF** via serial communication.

---

## 📸 Preview
A black-themed premium UI with cyan buttons:
- **TURN BUZZER ON**
- **TURN BUZZER OFF**
- Real-time status updates

---

## 🚀 Features

- 🎨 Premium dark UI using **PyQt5 stylesheets**
- 🔘 One-click **Buzzer ON / OFF**
- 🔄 Real-time status label updates
- 🔌 Serial communication with Arduino
- 🧠 Simple & beginner-friendly logic
- ⚡ Fast response via USB Serial (9600 baud)

---

## 🛠️ Technologies Used

- **Python 3**
- **PyQt5**
- **PySerial**
- **Arduino (UNO / Nano / Mega)**
- **Buzzer Module**

---

## 📂 Project Structure

```text
Premium-Buzzer-Controller/
│
├── buzzer_app.py        # Main Python GUI application
├── README.md            # Project documentation
└── Arduino_Code.ino     # Arduino sketch for buzzer control
COMPONENTS_USED = {
    "Microcontroller": "Arduino UNO / Nano / Mega",
    "Buzzer": "Active or Passive Buzzer",
    "Jumper_Wires": "Male-to-Male",
    "USB_Cable": "USB A to B",
    "Computer": "PC / Laptop",
    "Software": [
        "Python 3",
        "PyQt5",
        "PySerial",
        "Arduino IDE"
    ]
}
## HARDWARE_CONNECTIONS = {
    "Arduino_D8": "Buzzer Positive (+)",
    "Arduino_GND": "Buzzer Negative (-)"
}
// Arduino Pin Configuration
#define BUZZER_PIN 8
SERIAL_SETTINGS = {
    "Port": "COM3 / ttyUSB0 / usbmodem",
    "Baud_Rate": 9600,
    "Data_Type": "Character"
}
SERIAL_COMMANDS = {
    "1": "Turn Buzzer ON",
    "0": "Turn Buzzer OFF"
}
WORKING_LOGIC = [
    "User clicks GUI button",
    "PyQt5 sends serial command",
    "Arduino receives data",
    "Buzzer state changes",
    "Status updated in GUI"
]
SYSTEM_ARCHITECTURE = {
    "Input": "PyQt5 GUI",
    "Communication": "USB Serial",
    "Controller": "Arduino",
    "Output": "Buzzer"
}
DATA_FLOW = {
    "GUI_Button": "Send '1' or '0'",
    "USB": "Transmit serial data",
    "Arduino": "Process command",
    "Buzzer": "ON / OFF"
}
