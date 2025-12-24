# LMS-QT
### Link Media Server — Qt Desktop Client

LMS-QT is a cross-platform (macOS & Linux) Qt application that serves as both a frontend UI and a launcher for Link Media Server (LMS). It provides onboarding, configuration, and server management with GNOME-inspired theming.

## 🚀 Features

| Feature | Local Mode | Remote Mode |
|---------|-------------|--------------|
| Run `lms-runtime` directly from the app | ✅ | — |
| Connect to LMS on another device | — | ✅ |
| Dashboard & server status | ✅ | ✅ |
| Media browser (WIP) | ⚙️ | ⚙️ |
| First-run onboarding | 🧭 | 🧭 |
| Settings saved automatically | 💾 | 💾 |

## 📦 Requirements

**Runtime**
- macOS 12+ or Linux (GNOME recommended)
- Qt 6.2+
- `lms-runtime` binary (for Local mode)

**Development**
- CMake 3.16+
- Qt Creator or Qt dev tools
- C++17 compiler

## 🧭 Getting Started

### 1️⃣ Clone
```sh
git clone https://github.com/Link-Technologies-Limited/LMS-QT.git
cd LMS-QT
```

### 2️⃣ Build
```sh
mkdir build && cd build
cmake ..
cmake --build .
```

### 3️⃣ Run
```sh
./LMSQT
```

---

## 🖥️ First Launch (Onboarding)

Choose how the app should operate:

### Local Mode
Run your own server inside LMS-QT.
- Pick your `lms-runtime` path
- LMS-QT controls the process

### Remote Mode
Connect to another LMS instance.
- Enter server URL like:
```
http://192.168.1.59:8080
```

Settings stored in:
```
Linux: ~/.config/Blacklink/LMSQT/
macOS: ~/Library/Preferences/Blacklink/LMSQT/
```

---

## 🧩 Architecture

```
LMS-QT/
 ├─ src/
 │   ├─ main.cpp
 │   ├─ ServerController.*  → QProcess + API
 │
 ├─ qml/
 │   ├─ Main.qml
 │   ├─ OnboardingPage.qml
 │   ├─ DashboardPage.qml
 │   └─ components/
 │
 ├─ CMakeLists.txt
```

### Core Technologies
- QML / Qt Quick
- QProcess (run server)
- QNetworkAccessManager (API)
- GNOME/Adwaita-inspired visuals

---

## 🔌 Example Endpoints

```http
GET /api/status
GET /api/media
```

Basic ping from QML:
```qml
serverController.serverUrl = "http://192.168.1.59:8080"
serverController.pingServer()
```

---

## 🎨 Design Language

```
background: #18181b
surface:    #111827
border:     #27272f
text:       #e5e7eb
accent:     #38bdf8 (or #7c3aed)
radius:     14px–18px
```

---

## 📅 Roadmap

- **v0.1**: Onboarding, local/remote modes, status checks
- **v0.3**: Media browser, thumbnails
- **v0.5**: Playback, uploads
- **v1.0**: Auth, theming, Windows, installers

---

## 🤝 Contributing

PRs welcome!
Open issues on GitHub:
https://github.com/Link-Technologies-Limited/LMS-QT/issues

---

## 🏢 About

LMS-QT is part of the **Blacklink / Link Technologies** ecosystem:
- Link Media Server (LMS)
- Note26 / Blacklink NOVA
- SiS / Learn

