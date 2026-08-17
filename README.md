# 🌬️ AirGuard

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" width="85" alt="Flutter"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" width="85" alt="Firebase"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original.svg" width="85" alt="Dart"/>
</p>

<h3 align="center">
  IoT-Based Smart Factory Monitoring System
</h3>

<p align="center">
  A real-time factory monitoring application built with
  <b>Flutter, Firebase, ESP32, and IoT sensors.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white" alt="Flutter"/>
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white" alt="Dart"/>
  <img src="https://img.shields.io/badge/Firebase-Firestore-FFCA28?logo=firebase&logoColor=black" alt="Firebase"/>
  <img src="https://img.shields.io/badge/ESP32-IoT-E7352C?logo=espressif&logoColor=white" alt="ESP32"/>
  <img src="https://img.shields.io/badge/Platform-Web%20%7C%20Android-34A853" alt="Platform"/>
</p>

---

## 📖 About AirGuard

**AirGuard** is an IoT-based smart factory monitoring system designed to monitor machine conditions and environmental parameters in real time.

The system combines an **ESP32 microcontroller**, environmental sensors, **Firebase Cloud Firestore**, and a **Flutter application** to provide a centralized monitoring platform.

Sensor data collected from the factory environment is transmitted through the ESP32 and stored in Firebase. The Flutter application retrieves and listens to the Firestore data to display updated information to the user.

### 🎯 Project Objectives

AirGuard aims to provide:

* 🏭 Real-time machine monitoring
* 🌡️ Environmental monitoring
* 📡 IoT-based data collection
* ☁️ Cloud-based data storage
* 📊 Real-time dashboard visualization
* 🚨 Early identification of abnormal conditions
* 📱 A simple and user-friendly monitoring interface

---

# ✨ Key Features

## 🏭 Machine Status Monitoring

The system monitors different machine states:

| Status     | Meaning                                       |
| ---------- | --------------------------------------------- |
| 🟢 Running | Machine is operating normally                 |
| 🟡 Idle    | Machine is currently inactive                 |
| 🔴 Error   | Machine has encountered an abnormal condition |

Machine status information is stored in **Cloud Firestore** and displayed in the Flutter dashboard.

---

## 🌡️ Environmental Monitoring

AirGuard is designed to collect environmental data using IoT sensors such as:

* 🌡️ Temperature
* 💧 Humidity
* 🌫️ Air quality / gas level
* ⚙️ Machine-related sensor readings

---

## 📡 Real-Time Monitoring

The Flutter application listens to Firebase Firestore for updated data.

When new sensor information is available, the application can automatically update the displayed values without requiring a manual refresh.

---

## ☁️ Cloud Data Storage

Firebase Cloud Firestore is used to store:

* Machine states
* Sensor readings
* Environmental data
* Timestamps
* Other monitoring information

---

## 📱 Cross-Platform Application

The project is developed using Flutter and can be configured to run on:

* Android
* Web
* Windows

---

# 🏗️ System Architecture

```text
                    ┌──────────────────────┐
                    │   Factory Sensors    │
                    │                      │
                    │ 🌡️ Temperature       │
                    │ 💧 Humidity          │
                    │ 🌫️ Air Quality       │
                    │ ⚙️ Machine Data      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │        ESP32         │
                    │                      │
                    │ Sensor Reading       │
                    │ Data Processing      │
                    │ Wi-Fi Communication  │
                    └──────────┬───────────┘
                               │
                               │ Wi-Fi
                               ▼
                    ┌──────────────────────┐
                    │       Firebase       │
                    │      Firestore       │
                    │                      │
                    │ Machine Status       │
                    │ Sensor Readings      │
                    │ Real-Time Data       │
                    └──────────┬───────────┘
                               │
                               │ Real-Time Stream
                               ▼
                    ┌──────────────────────┐
                    │     Flutter App      │
                    │                      │
                    │ 📊 Dashboard         │
                    │ ⚙️ Machine Details   │
                    │ 🌡️ Sensor Data       │
                    │ 📈 Monitoring        │
                    └──────────────────────┘
```

---

# 🔄 Data Flow

```text
IoT Sensor
    ↓
ESP32
    ↓
Wi-Fi
    ↓
Firebase Firestore
    ↓
Flutter Firestore Listener
    ↓
Dashboard
    ↓
User
```

### Process

1. Sensors collect physical/environmental measurements.
2. ESP32 reads the sensor values.
3. ESP32 communicates with the cloud through Wi-Fi.
4. Sensor information is stored in Firebase Firestore.
5. Flutter retrieves/listens to Firestore data.
6. The dashboard displays the latest available information.

---

# 🔧 Hardware Components

| Component              | Purpose                                                |
| ---------------------- | ------------------------------------------------------ |
| **ESP32**              | Main IoT controller and Wi-Fi communication            |
| **DHT11**              | Temperature and humidity measurement                   |
| **MQ135**              | Air quality / gas monitoring                           |
| **Power Supply**       | Provides power to the IoT system                       |
| **Additional Sensors** | Can be integrated according to monitoring requirements |

---

# 💻 Technology Stack

### 🎨 Frontend

<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" width="50" alt="Flutter"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original.svg" width="50" alt="Dart"/>
</p>

* Flutter
* Dart
* Material Design
* Responsive UI

### ☁️ Backend & Cloud

<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" width="50" alt="Firebase"/>
</p>

* Firebase
* Cloud Firestore
* Real-time data synchronization

### 🤖 IoT

* ESP32
* Wi-Fi
* DHT11
* MQ135
* Environmental sensors

### 🛠️ Development Tools

* Visual Studio Code
* Arduino IDE
* Git
* GitHub

---

# 📂 Project Structure

```text
airguard_new/
│
├── android/
├── ios/
├── web/
├── windows/
│
├── lib/
│   ├── main.dart
│   ├── firebase_options.dart
│   │
│   ├── models/
│   │
│   ├── screens/
│   │
│   ├── services/
│   │   └── firestore_service.dart
│   │
│   └── widgets/
│
├── assets/
│
├── test/
│
├── pubspec.yaml
├── README.md
└── .gitignore
```

> The project structure may evolve as new features are added.

---

# ☁️ Firebase Firestore

AirGuard uses **Cloud Firestore** as its cloud database.

A possible database organization is:

```text
Firestore
│
├── machines
│   │
│   ├── machine_01
│   │   ├── name
│   │   ├── status
│   │   └── updatedAt
│   │
│   └── machine_02
│       ├── name
│       ├── status
│       └── updatedAt
│
└── sensors
    │
    ├── temperature
    ├── humidity
    └── airQuality
```

The Flutter application communicates with Firestore to display the latest monitoring information.

---

# 📊 Dashboard

The AirGuard dashboard provides a centralized view of the factory environment.

Example dashboard information:

```text
┌─────────────────────────────────────────┐
│             AIRGUARD DASHBOARD          │
├─────────────────────────────────────────┤
│                                         │
│   🟢 RUNNING    🟡 IDLE    🔴 ERROR    │
│                                         │
│   🌡️ Temperature        28°C            │
│   💧 Humidity           65%             │
│   🌫️ Air Quality        Normal          │
│                                         │
└─────────────────────────────────────────┘
```

Future dashboard improvements can include:

* 📈 Historical sensor charts
* 🚨 Warning indicators
* 🔔 Notifications
* 📊 Statistical analysis
* 🏭 Multiple machine monitoring

---

# 🚀 Getting Started

## Prerequisites

Make sure you have installed:

* Flutter SDK
* Dart SDK
* Android Studio / Android SDK
* Visual Studio Code
* Git
* Firebase project

Check Flutter installation:

```bash
flutter doctor
```

---

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/Rupu-s/airguard_new.git
```

Navigate to the project:

```bash
cd airguard_new
```

---

## 2️⃣ Install Dependencies

```bash
flutter pub get
```

---

## 3️⃣ Configure Firebase

Make sure the project is connected to the correct Firebase project.

Firebase configuration should be set up for the target platform before running the application.

---

## 4️⃣ Check Available Devices

```bash
flutter devices
```

---

## 5️⃣ Run the Application

### Chrome

```bash
flutter run -d chrome
```

### Android

```bash
flutter run
```

---

# 🌐 Build for Web

To create a production web build:

```bash
flutter build web
```

The generated files will be located at:

```text
build/web/
```

---

# 📱 Build for Android

### Debug APK

```bash
flutter build apk
```

### Release APK

```bash
flutter build apk --release
```

### Android App Bundle

For Google Play Store deployment:

```bash
flutter build appbundle
```

---

# 🔐 Security

Security is an important part of an IoT cloud application.

Never upload sensitive credentials such as:

* ❌ Private keys
* ❌ Service account JSON files
* ❌ Passwords
* ❌ Authentication secrets
* ❌ Private credentials

Firebase **Security Rules** should be configured appropriately before deploying the system for public use.

---

# 🧪 Project Status

| Feature                  | Status            |
| ------------------------ | ----------------- |
| Flutter Application      | ✅ Implemented     |
| Firebase Integration     | ✅ Implemented     |
| Cloud Firestore          | ✅ Implemented     |
| Real-Time Data           | ✅ Implemented     |
| Machine Monitoring       | 🔄 In Development |
| ESP32 Integration        | 🔄 In Development |
| Environmental Monitoring | 🔄 In Development |
| Web Deployment           | 🚧 Planned        |
| Android Release          | 🚧 Planned        |

---

# 🛣️ Future Improvements

The following features may be added in future versions:

* 📈 Historical data visualization
* 🚨 Automatic abnormal-condition detection
* 🔔 Push notifications
* 📊 Advanced analytics
* 🏭 Multiple factory support
* 👤 User authentication
* 🔐 Role-based access control
* 📱 Improved mobile interface
* 🌐 Public web dashboard
* 📡 Additional IoT sensors
* 🧠 Predictive maintenance
* 🤖 AI-based anomaly detection

---

# 👥 Contributors

This project is developed as a collaborative IoT and Robotics Engineering project.

### Contributors

| Contributor              | GitHub                                                 |
| ------------------------ | ------------------------------------------------------ |
| **Rupu**                 | [@Rupu-s](https://github.com/Rupu-s)                   |
| **Pritom Kumar Bhowmik** | [@pritom05-crypto](https://github.com/pritom05-crypto) |

<p align="center">
  <a href="https://github.com/Rupu-s">
    <img src="https://github.com/Rupu-s.png" width="80" height="80" alt="Rupu"/>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/pritom05-crypto">
    <img src="https://github.com/pritom05-crypto.png" width="80" height="80" alt="Pritom"/>
  </a>
</p>

---

# 📜 License

This project is developed for **educational and research purposes**.

---

# ⭐ Support the Project

If you find **AirGuard** useful or interesting, consider giving this repository a ⭐ on GitHub.

<p align="center">

## 🌬️ AirGuard

### Smart Monitoring. Real-Time Insights. Safer Factories.

Built with ❤️ using Flutter, Firebase & IoT.

</p>
