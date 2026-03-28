<div align="center">

<!-- HERO BANNER -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0800,50:2d1500,100:1a0400&height=200&section=header&text=Premium%20Buzzer%20Controller&fontSize=44&fontColor=ffffff&fontAlignY=38&desc=Arduino%20%2B%20Python%20GUI%20%E2%80%A2%20PC-Controlled%20Hardware%20via%20Serial%20USB&descAlignY=58&descSize=16" width="100%"/>

<br/>

<!-- BADGES ROW 1 -->
[![Arduino](https://img.shields.io/badge/Hardware-Arduino-f97316?style=for-the-badge&logo=arduino&logoColor=white)](https://arduino.cc)
[![Python](https://img.shields.io/badge/GUI-Python%20%2B%20PyQt5-fbbf24?style=for-the-badge&logo=python&logoColor=black)](https://python.org)
[![Status](https://img.shields.io/badge/Status-Active-f97316?style=for-the-badge&logo=statuspage&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-ef4444?style=for-the-badge)](LICENSE)

<!-- BADGES ROW 2 -->
[![GitHub](https://img.shields.io/badge/GitHub-mebdulrafay-181717?style=flat-square&logo=github)](https://github.com/mebdulrafay)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Hafiz%20Abdul%20Rafay-0A66C2?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/hafiz-abdul-rafay-4577a5395/)
[![Email](https://img.shields.io/badge/Email-mebdulrafay@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:mebdulrafay@gmail.com)
[![HP LIFE](https://img.shields.io/badge/Certified-HP%20LIFE%20AI-0096D6?style=flat-square&logo=hp&logoColor=white)]()

<br/>

> **Premium Buzzer Controller** is a hardware-meets-software project by **Hafiz Abdul Rafay** — a sleek Python GUI that sends commands over USB serial to an Arduino, toggling a physical buzzer ON and OFF in real time.

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Project Components](#-project-components)
- [How It Works](#-how-it-works)
- [Serial Communication Protocol](#-serial-communication-protocol)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [About the Author](#-about-the-author)

---

## 🌐 Overview

**Premium Buzzer Controller** is a complete Arduino–Python integration project where a **desktop GUI** controls a **hardware buzzer** through **USB serial communication**. It demonstrates the bridge between software UI and physical hardware — a core concept in embedded systems and IoT development.

```
User Clicks Button  ──►  Python GUI (PyQt5)  ──►  Serial USB  ──►  Arduino  ──►  Buzzer
                               │                                        │
                    ┌──────────┴──────────┐                  ┌─────────┴─────────┐
                    ▼                     ▼                  ▼                   ▼
              TURN ON ('1')        TURN OFF ('0')       Pin HIGH             Pin LOW
              Status Update        Status Update       Buzzer ON           Buzzer OFF
```

### ✨ What This Project Does

- 🔔 **Toggle a physical buzzer** ON/OFF from a PC desktop button
- 🖥️ **Real-time status display** — GUI updates to reflect current buzzer state
- 🔌 **Serial USB bridge** — Python talks to Arduino at 9600 baud
- 🎨 **Premium dark GUI** — black background, cyan accents, Montserrat font
- ⚡ **Instant response** — single-byte serial command triggers immediate hardware action

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                  BUZZER CONTROLLER — SYSTEM ARCHITECTURE             │
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│   ┌──────────────────────────────────────────────────────────────┐  │
│   │                   PC LAYER (Python / PyQt5)                   │  │
│   │                                                               │  │
│   │   ┌─────────────┐   click    ┌────────────────────────────┐  │  │
│   │   │  ON Button  │──────────► │  buzzer_on()               │  │  │
│   │   └─────────────┘            │  arduino.write(b'1')        │  │  │
│   │                              │  status → "Buzzer is ON"    │  │  │
│   │   ┌─────────────┐   click    └────────────┬───────────────┘  │  │
│   │   │  OFF Button │──────────► buzzer_off() │ write(b'0')      │  │
│   │   └─────────────┘            └────────────┘                  │  │
│   └──────────────────────────────────┬───────────────────────────┘  │
│                                      │ USB Serial (COM3 / 9600 baud) │
│   ┌──────────────────────────────────▼───────────────────────────┐  │
│   │                  HARDWARE LAYER (Arduino)                     │  │
│   │                                                               │  │
│   │   Serial.read() ──► Is '1'? ──► digitalWrite(PIN, HIGH)      │  │
│   │                  └─ Is '0'? ──► digitalWrite(PIN, LOW)       │  │
│   │                                                               │  │
│   │              [ BUZZER ] ◄── Digital Output Pin               │  │
│   └───────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🛠 Tech Stack

### 🖥️ Software (PC Side)

| Technology | Role | Version |
|:---:|:---|:---:|
| ![Python](https://img.shields.io/badge/Python-GUI_Logic-f97316?style=flat-square&logo=python&logoColor=white) | Application logic & serial communication | 3.x |
| ![PyQt5](https://img.shields.io/badge/PyQt5-Desktop_GUI_Framework-fbbf24?style=flat-square&logo=qt&logoColor=black) | Window, buttons, labels, layout | Latest |
| ![PySerial](https://img.shields.io/badge/PySerial-USB_Serial_Comms-ef4444?style=flat-square&logo=python&logoColor=white) | Serial port communication with Arduino | Latest |

### ⚙️ Hardware (Arduino Side)

| Component | Role | Notes |
|:---:|:---|:---:|
| ![Arduino](https://img.shields.io/badge/Arduino_UNO-Microcontroller-f97316?style=flat-square&logo=arduino&logoColor=white) | Receives serial commands & drives buzzer | Any Arduino board |
| ![Buzzer](https://img.shields.io/badge/Passive_Buzzer-Audio_Output-fbbf24?style=flat-square) | Physical output device | Connected to digital pin |
| ![USB](https://img.shields.io/badge/USB_Serial-COM3_%40_9600_baud-ef4444?style=flat-square) | Communication bridge between PC & Arduino | Standard USB cable |

### 🌐 Abdul Rafay's Core Tech (Portfolio)

| Category | Technologies |
|:---|:---|
| **Frontend** | ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3) ![JavaScript](https://img.shields.io/badge/JavaScript_ES6+-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| **Python** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyQt5](https://img.shields.io/badge/PyQt5-41CD52?style=flat-square&logo=qt) ![CustomTkinter](https://img.shields.io/badge/CustomTkinter-blue?style=flat-square) |
| **Hardware / IoT** | ![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white) Servo • Ultrasonic Sensors • Serial Comm |
| **Design** | Glassmorphism • Branding • Social Media Creatives |
| **AI/Automation** | ![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n) Google Gemini • LangChain Agents |

---

## 🔩 Project Components

| # | Component | Language | Description |
|:---:|:---|:---:|:---|
| 1 | **BuzzerApp (GUI)** | Python | PyQt5 `QWidget` with ON/OFF buttons and a live status label |
| 2 | **Serial Connection** | Python | `serial.Serial('COM3', 9600)` opens the USB port to the Arduino |
| 3 | **buzzer_on()** | Python | Writes `b'1'` to serial and updates the status label |
| 4 | **buzzer_off()** | Python | Writes `b'0'` to serial and updates the status label |
| 5 | **Arduino Sketch** | C/C++ | Reads serial byte — `'1'` sets pin HIGH, `'0'` sets pin LOW |
| 6 | **Buzzer Hardware** | Electronics | Connected to a digital output pin on the Arduino board |

---

## ⚡ How It Works

### Complete Project Flow

```
┌──────────────────────┐
│        START         │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Launch Python GUI    │
│ (PyQt5 Application)  │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ User Clicks Button   │
│   ON   or   OFF      │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Python Sends Serial  │
│  Data: '1' or '0'   │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│ Arduino Receives     │
│   Serial Command     │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│  Is Command = '1' ?  │
└───────┬──────────────┘
     YES │           NO
        ▼             ▼
┌──────────────┐  ┌──────────────┐
│  Buzzer ON   │  │  Buzzer OFF  │
│ (Pin HIGH)   │  │  (Pin LOW)   │
└──────┬───────┘  └──────┬───────┘
       └──────────────────┘
                  ▼
┌──────────────────────┐
│  Update GUI Status   │
└──────────┬───────────┘
           ▼
┌──────────────────────┐
│         END          │
└──────────────────────┘
```

---

## 📡 Serial Communication Protocol

The entire software-to-hardware channel runs on a single-byte protocol over USB serial:

| Command Sent | Python Code | Arduino Response | Buzzer State |
|:---:|:---:|:---|:---:|
| `'1'` (byte) | `arduino.write(b'1')` | `digitalWrite(buzzerPin, HIGH)` | 🔔 **ON** |
| `'0'` (byte) | `arduino.write(b'0')` | `digitalWrite(buzzerPin, LOW)` | 🔕 **OFF** |

### Python Side (Key Code)
```python
import serial
from PyQt5.QtWidgets import QApplication, QWidget, QPushButton, QLabel, QVBoxLayout

arduino = serial.Serial('COM3', 9600)   # Open serial port at 9600 baud

def buzzer_on(self):
    self.status_label.setText("Status: Buzzer is ON")
    arduino.write(b'1')                 # Sends '1' → Arduino turns buzzer ON

def buzzer_off(self):
    self.status_label.setText("Status: Buzzer is OFF")
    arduino.write(b'0')                 # Sends '0' → Arduino turns buzzer OFF
```

### Arduino Side (Logic)
```cpp
int buzzerPin = 8;

void setup() {
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  if (Serial.available() > 0) {
    char cmd = Serial.read();
    if (cmd == '1') digitalWrite(buzzerPin, HIGH);  // Buzzer ON
    if (cmd == '0') digitalWrite(buzzerPin, LOW);   // Buzzer OFF
  }
}
```

---

## 📸 GUI Layout

```
┌─────────────────────────────────┐
│       Buzzer Controller          │   ← Title (Montserrat Bold 16)
│                                 │
│  Status: Waiting for action...  │   ← Live Status Label
│                                 │
│  ┌───────────────────────────┐  │
│  │     TURN BUZZER ON        │  │   ← Cyan Button (#00ffff)
│  └───────────────────────────┘  │
│                                 │
│  ┌───────────────────────────┐  │
│  │     TURN BUZZER OFF       │  │   ← Cyan Button (#00ffff)
│  └───────────────────────────┘  │
│                                 │
│   Background: Black (#000000)   │
└─────────────────────────────────┘
   Window Size: 400 × 300 px
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x installed
- Arduino IDE installed
- Arduino UNO (or compatible board)
- A passive buzzer component
- USB cable (Arduino to PC)

### Installation

**1. Clone this repository**
```bash
git clone https://github.com/mebdulrafay/Arduino-Based-PC-Controlled-Buzzer.git
cd Arduino-Based-PC-Controlled-Buzzer
```

**2. Install Python dependencies**
```bash
pip install PyQt5 pyserial
```

**3. Upload the Arduino sketch**
```
Arduino IDE → Open sketch → Upload to board
Wire the buzzer to digital pin 8 (or update buzzerPin in sketch)
```

**4. Check your COM port**
```
Windows: Device Manager → Ports (COM & LPT) → find your Arduino's port
Update in code:  arduino = serial.Serial('COM3', 9600)
                                          ^^^^
                                  Change to your port
```

**5. Run the Python GUI**
```bash
python "BUZZER APP CODE.txt"
```

**6. Test it!**
```
Click  [ TURN BUZZER ON ]   → Buzzer beeps  🔔
Click  [ TURN BUZZER OFF ]  → Buzzer stops  🔕
```

---

## ⚙️ Configuration

### Port & Baud Rate

Adjust the serial connection at the top of the Python file:

```python
arduino = serial.Serial('COM3', 9600)
#                         ^^^^   ^^^^
#                     COM port  Baud rate (must match Arduino sketch)
```

| Setting | Default | Notes |
|:---|:---:|:---|
| COM Port | `COM3` | Change to match your system (e.g. `COM5`, `/dev/ttyUSB0` on Linux) |
| Baud Rate | `9600` | Must match `Serial.begin(9600)` in Arduino sketch |
| Buzzer Pin | `8` | Change `buzzerPin` in Arduino sketch to match wiring |

### GUI Theme

The dark aesthetic is configured via inline Qt stylesheets:

```python
BACKGROUND    = "black"      # Window background
BUTTON_COLOR  = "#00ffff"    # Cyan accent buttons
BUTTON_HOVER  = "#00cccc"    # Hover state (slightly darker)
TEXT_COLOR    = "white"      # All label text
FONT          = "Montserrat" # Font family
```

---

## 👨‍💻 About the Author

<div align="center">

| Field | Detail |
|:---:|:---|
| **Name** | Hafiz Abdul Rafay |
| **Role** | Student • AI-Assisted Web Developer • Freelancer |
| **Location** | 📍 Mianwali, Pakistan |
| **Achievement** | 🏆 2nd Place — Science Expo 2025, PAEC Education Center (Level VI–VIII) |
| **Certification** | 🎓 HP LIFE Certified — AI's Business Impact & Ethics |

</div>

### 🤝 Connect with Abdul Rafay

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-mebdulrafay-181717?style=for-the-badge&logo=github)](https://github.com/mebdulrafay)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/hafiz-abdul-rafay-4577a5395/)
[![Email](https://img.shields.io/badge/Email-Say%20Hello!-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:mebdulrafay@gmail.com)

</div>

---

### 📌 Full Project Portfolio

| Project | Stack | Description |
|:---|:---|:---|
| 🎯 **Radar System** | Arduino • Ultrasonic Sensor | Object detection with AI voice alerts & real-time distance feedback |
| 🌦 **Weather Forecast App** | HTML/CSS/JS • OpenWeather API | Responsive live weather app with dynamic UI |
| 🔢 **Binary X** | Python • PyQt5 | Desktop app for efficient text-to-binary conversion |
| 🔔 **PC-Controlled Buzzer** | Arduino • Python • PySerial | *This project* — Hardware alert system controlled via PC GUI |
| 🌐 **Personal Portfolio** | HTML/CSS/JS • Glassmorphism | Premium interactive site showcasing all digital & hardware projects |
| 🤖 **ROEX AI Assistant** | n8n • Gemini • LangChain | AI-powered portfolio representative with memory & GitHub integration |

---

### 💼 Freelancing Services

| Service | Description |
|:---|:---|
| 🌐 Modern Web Development | Responsive & premium UI/UX with glassmorphism aesthetics |
| 🤖 AI-Assisted Development | Faster turnaround using AI-powered n8n workflows |
| ⚡ Arduino & IoT Prototyping | Sensor integration, serial comms, and hardware projects |
| 🎨 Graphic Design & Branding | Social media creatives, logos, and visual identity |

> 📬 Interested in working together? Reach out at **mebdulrafay@gmail.com**

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a0400,50:2d1500,100:0f0800&height=100&section=footer" width="100%"/>

**Made with 🧡 by [Hafiz Abdul Rafay](https://github.com/mebdulrafay) — Mianwali, Pakistan**

*"Specializing in elegant solutions that combine beautiful design with powerful functionality."*

⭐ **Star this repo if the buzzer beeped its way into your heart!**

</div>
