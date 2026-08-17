# 🌬️ AirGuard — Smart Factory Monitoring System

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" width="90" alt="Flutter Logo"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" width="90" alt="Firebase Logo"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original.svg" width="90" alt="Dart Logo"/>
</p>

<p align="center">
  <b>IoT-Based Smart Factory Monitoring & Environmental Safety System</b>
</p>

<p align="center">
  A real-time monitoring application built with Flutter, Firebase, ESP32, and environmental sensors.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dart-3.x-0175C2?logo=dart&logoColor=white"/>
  <img src="https://img.shields.io/badge/Firebase-Firestore-FFCA28?logo=firebase&logoColor=black"/>
  <img src="https://img.shields.io/badge/ESP32-IoT-E7352C?logo=espressif&logoColor=white"/>
  <img src="https://img.shields.io/badge/Platform-Web%20%7C%20Android-34A853"/>
</p>

---

## 📖 About the Project

**AirGuard** is an IoT-based smart factory monitoring system designed to monitor machine conditions and environmental parameters in real time.

The system combines an **ESP32 microcontroller**, environmental sensors, **Firebase Cloud Firestore**, and a **Flutter application** to provide a centralized monitoring dashboard.

Sensor data collected from the factory environment is transmitted through the ESP32 and stored in Firebase. The Flutter application then listens to the Firebase database and displays the latest information in real time.

### 🎯 Main Goal

The main goal of AirGuard is to provide a simple and efficient way to:

* Monitor factory machine status
* Monitor temperature and environmental conditions
* Receive real-time sensor updates
* Store IoT data in the cloud
* Visualize factory conditions through a modern dashboard
* Help identify abnormal conditions quickly

---

## ✨ Key Features

### 🏭 Machine Monitoring

Monitor the current state of factory machines:

* 🟢 **Running**
* 🟡 **Idle**
* 🔴 **Error**

Machine status is stored in **Cloud Firestore** and displayed on the Flutter dashboard.

### 🌡️ Environmental Monitoring

The system can collect environmental data using sensors such as:

* Temperature
* Humidity
* Air quality / gas level
* Other connected IoT sensor readings

### 📡 Real-Time Data

Flutter listens to Firestore for changes, allowing the dashboard to update automatically whenever new sensor data arrives.

### ☁️ Cloud Database

Firebase Cloud Firestore is used to:

* Store machine states
* Store sensor readings
* Synchronize data
* Provide real-time updates

### 📱 Cross-Platform Application

The application is developed using Flutter and can be configured for:

* Android
* Web
* Windows

---

# 🏗️ System Architecture

```text
              ┌─────────────────────┐
              │   Factory Sensors   │
              │                     │
              │ 🌡️ Temperature      │
              │ 💧 Humidity         │
              │ 🌫️ Air Quality      │
              │ ⚙️ Machine Data     │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │       ESP32         │
              │                     │
              │ Sensor Data         │
              │ Processing          │
              │ Wi-Fi Communication │
              └──────────┬──────────┘
                         │
                         │ Wi-Fi
                         ▼
              ┌─────────────────────┐
              │      Firebase       │
              │     Firestore       │
              │                     │
              │ Machine Status      │
              │ Sensor Readings     │
              │ Real-Time Data      │
              └──────────┬──────────┘
                         │
                         │ Real-Time Stream
                         ▼
              ┌─────────────────────┐
              │    Flutter App      │
              │                     │
              │ 📊 Dashboard        │
              │ ⚙️ Machine Details  │
              │ 🌡️ Sensor Data      │
              │ 📈 Monitoring       │
              └─────────────────────┘
```

---

# 🔧 Hardware Components

| Component           | Purpose                                     |
| ------------------- | ------------------------------------------- |
| **ESP32**           | Main IoT controller and Wi-Fi communication |
| **DHT11**           | Temperature and humidity measurement        |
| **MQ135**           | Air quality / gas monitoring                |
| **Power Supply**    | Provides power to the IoT hardware          |
| **Factory Sensors** | Collect machine/environmental information   |

> Additional sensors can be integrated into the system depending on the factory monitoring requirements.

---

# 💻 Technology Stack

## Frontend

<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" width="45"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dart/dart-original.svg" width="45"/>
</p>

* **Flutter**
* **Dart**
* Material Design
* Responsive UI

## Backend / Cloud

<p>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" width="45"/>
</p>

* Firebase
* Cloud Firestore
* Real-time data synchronization

## IoT

* ESP32
* Wi-Fi
* DHT11
* MQ135
* Environmental sensors

## Development Tools

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
│   ├── services/
│   │   └── firestore_service.dart
│   │
│   ├── screens/
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

> The exact folder structure may change as the project develops.

---

# ☁️ Firebase Integration

AirGuard uses **Cloud Firestore** as the central cloud database.

A typical data structure can be organized as:

```text
Firestore
│
├── machines
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
    ├── temperature
    ├── humidity
    └── airQuality
```

The Flutter application reads this data using the Firebase/Firestore integration.

---

# 🔄 Data Flow

The complete data flow is:

```text
Sensor
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

When the ESP32 sends new data:

1. The sensor measures the physical parameter.
2. ESP32 reads the sensor value.
3. ESP32 sends the data through Wi-Fi.
4. Firebase stores the latest value.
5. Flutter listens to Firestore.
6. Dashboard updates automatically.

---

# 📊 Application Dashboard

The dashboard is designed to provide a quick overview of the factory environment.

It can display:

```text
┌──────────────────────────────────────┐
│          AIRGUARD DASHBOARD          │
├──────────────────────────────────────┤
│                                      │
│  🟢 Running     🟡 Idle    🔴 Error │
│                                      │
│  🌡️ Temperature       28°C           │
│  💧 Humidity          65%            │
│  🌫️ Air Quality       Normal         │
│                                      │
└──────────────────────────────────────┘
```

The UI can be extended with:

* Machine cards
* Sensor cards
* Status indicators
* Warning indicators
* Historical charts
* Real-time readings

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/Rupu-s/airguard_new.git
```

Navigate to the project:

```bash
cd airguard_new
```

## 2. Install Flutter Dependencies

```bash
flutter pub get
```

## 3. Configure Firebase

Make sure your Firebase project is configured for the application.

The project uses Firebase configuration generated for Flutter.

For a new Firebase project, configure Firebase according to your target platform.

## 4. Check Connected Devices

```bash
flutter devices
```

## 5. Run the Application

For Chrome:

```bash
flutter run -d chrome
```

For Android:

```bash
flutter run
```

---

# 🌐 Build for Web

To create a production web build:

```bash
flutter build web
```

The generated web files will be available inside:

```text
build/web/
```

---

# 📱 Build for Android

To generate an APK:

```bash
flutter build apk
```

For a release APK:

```bash
flutter build apk --release
```

For Google Play Store deployment, an Android App Bundle can be generated using:

```bash
flutter build appbundle
```

---

# 🔐 Security

Firebase credentials and sensitive configuration must be handled carefully.

Do not upload:

* Private keys
* Service account JSON files
* Passwords
* Authentication secrets
* Private API credentials

Firebase **Security Rules** should also be configured properly before deploying the application for public use.

---

# 🧪 Development Status

| Feature                   | Status            |
| ------------------------- | ----------------- |
| Flutter UI                | ✅ Implemented     |
| Firebase Integration      | ✅ Implemented     |
| Firestore Data            | ✅ Implemented     |
| Real-Time Monitoring      | ✅ Implemented     |
| ESP32 Integration         | 🔄 In Development |
| Environmental Sensors     | 🔄 In Development |
| Machine Status Monitoring | 🔄 In Development |
| Web Deployment            | 🚧 Planned        |
| Android Release           | 🚧 Planned        |

---

# 🛣️ Future Improvements

Future versions of AirGuard may include:

* 📈 Historical sensor-data charts
* 🚨 Automatic abnormal-condition alerts
* 🔔 Push notifications
* 📊 Advanced analytics
* 🏭 Multiple factory support
* 👤 User authentication
* 🔐 Role-based access control
* 📱 Improved mobile UI
* 🌐 Public web dashboard
* 📡 More IoT sensors
* 🧠 Predictive maintenance
* 🤖 AI-based anomaly detection

---

# 👥 Team

**AirGuard — IoT & Smart Factory Monitoring Project**

Developed as an IoT and Robotics Engineering project.

### Contributors

* **Rupu**
* Add other team members here

---

# 📜 License

This project is developed for educational and research purposes.

You may modify and extend the project according to your requirements.

---

# ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

<p align="center">

### 🌬️ AirGuard

**Smart Monitoring. Real-Time Insights. Safer Factories.**

</p>
