<div align="center">

<img src="app/src/main/res/drawable/ic_grown_tree.xml" alt="Atom Digital Detox" width="120" height="120"/>

# 🌳 Atom Digital Detox

### *Reclaim Your Focus. Grow Your Mind.*

[![Android](https://img.shields.io/badge/Platform-Android-brightgreen?style=for-the-badge&logo=android)](https://www.android.com)
[![Min SDK](https://img.shields.io/badge/Min%20SDK-24%20(Nougat)-blue?style=for-the-badge)](https://developer.android.com/about/versions/nougat)
[![Java](https://img.shields.io/badge/Language-Java-orange?style=for-the-badge&logo=java)](https://www.java.com)
[![License](https://img.shields.io/badge/License-MIT-purple?style=for-the-badge)](LICENSE)

> **Atom Digital Detox** is a gamified Android app that helps you fight phone addiction by turning your focus sessions into a growing tree. Stay off your phone — your tree thrives. Get distracted — your tree withers. 🌿

</div>

---

## 📱 What is Atom Digital Detox?

In today's world, phone addiction is real. We unlock our phones hundreds of times a day, breaking concentration, interrupting work, and draining productivity. **Atom Digital Detox** fights back — beautifully.

Inspired by focus-tree apps, Atom Digital Detox monitors your phone usage in real-time using Android's UsageStats API. When you commit to a detox session, a **sapling is planted**. If you stay focused and resist opening other apps, your tree **grows tall and strong**. But if you stray? It **withers**.

It's a simple, powerful visual metaphor that taps into your desire for progress and completion.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🌱 **Tree Growth System** | Start a session and watch your sapling grow into a full tree as time passes |
| ⏱️ **Customizable Timer** | Set your detox duration from **1 to 90 minutes** |
| 🔔 **Smart Notifications** | Stay notified of your session progress — even when the screen is off |
| 🚫 **App Detection** | Real-time foreground app monitoring using `UsageStatsManager` |
| ⚠️ **Distraction Countdown** | Switch apps and get an **11-second warning** to return before your tree withers |
| 🔕 **Do Not Disturb Mode** | Optional DND integration to silence notifications during your session |
| 📊 **Circular Progress Bar** | Visual timer display with smooth animated progress arc |
| 🔋 **Battery Optimization Bypass** | Ensures the background service keeps running uninterrupted |
| 🌿 **Result Screen** | Celebrate your success or try again upon session completion |

---

## 🎮 How It Works

```
1. Open App → Configure your session (set timer + optional DND)
2. Tap "Start the Detox!" → A sapling is planted 🌱
3. Stay on Atom Digital Detox → Your tree grows... 🌿 → 🌳
4. Switch to another app? → 11-second warning countdown begins! ⚠️
5. Return in time → Your tree survives 💚
6. Don't return in time → Your tree withers 💀 (try again!)
7. Complete the session → 🎉 Congratulations, your tree has fully grown!
```

---

## 📸 App Flow

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  ⚙️ Settings     │───▶│  ⏱️  Timer        │───▶│  🏆  Result      │
│                 │    │                 │    │                 │
│  Set Duration   │    │  Live Countdown │    │  Success 🌳     │
│  Enable DND     │    │  Circular Prog. │    │  or Failure 🥀  │
│  Start Detox!   │    │  Give Up option │    │  Try Again?     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Java (Android) |
| **Min SDK** | API 24 (Android 7.0 Nougat) |
| **Target SDK** | API 29 (Android 10) |
| **Architecture** | Single-Activity + Fragment-based (JSON State Machine) |
| **Event Bus** | GreenRobot EventBus 3.2 |
| **Serialization** | Gson 2.8.6 |
| **Parceling** | Parceler 1.1.12 |
| **Boilerplate Reduction** | Lombok 1.18.10 |
| **UI Components** | CircularProgressBar, Custom RoundedIconButton |
| **Storage** | SharedPreferences (via SharedPrefManager) |
| **Background** | Foreground Service + NotificationListenerService |

---

## 🚀 Getting Started

### Prerequisites
- Android Studio **Arctic Fox** or newer
- Android device / emulator running **API 24+**
- Java **1.8+**

### Installation

```bash
# 1. Clone this repository
git clone https://github.com/Ashutosh5917/final-_Project.git

# 2. Open in Android Studio
#    File → Open → Select cloned folder

# 3. Sync Gradle and build
./gradlew assembleDebug

# 4. Install on device
./gradlew installDebug
```

### Required Permissions (Granted Manually)

On first launch, the app will guide you to grant:

| Permission | Why Needed |
|---|---|
| **Usage Access** | Detect which app is in the foreground |
| **Notification Access** | Display progress and warning notifications |
| **Battery Optimization Bypass** | Keep background service alive |

---

## 📂 Project Structure

```
CellAddict/
├── app/src/main/
│   ├── java/com/subconscious/atomdigitaldetox/
│   │   ├── DetoxApplication.java          # App entry, lifecycle setup
│   │   ├── DigitalDetoxActivity.java      # Main activity, JSON flow router
│   │   ├── fragments/
│   │   │   ├── DetoxSettingsFragment.java # Session configuration screen
│   │   │   ├── DetoxTimerFragment.java    # Live timer with circular progress
│   │   │   └── DetoxResultFragment.java   # Success / failure result screen
│   │   ├── services/
│   │   │   ├── DigitalDetoxService.java   # Background foreground app monitor
│   │   │   └── NotificationListenerService.java
│   │   ├── helper/
│   │   │   ├── UsageUtils.java            # UsageStatsManager wrapper
│   │   │   ├── PermissionUtil.java        # Permission checks & requests
│   │   │   └── AtomNotificationManager.java
│   │   └── store/
│   │       └── SharedPrefManager.java     # Persistent session storage
│   └── res/
│       ├── layout/                        # XML screen layouts
│       ├── drawable/                      # Tree SVG icons & backgrounds
│       ├── anim/                          # Slide & fade animations
│       └── font/                          # Montserrat & Sen typography
```

---

## 🔮 Roadmap / Future Improvements

- [ ] 🔗 Cloud sync & session history dashboard
- [ ] 🪙 Streak system — consecutive successful detox rewards
- [ ] 🌲 Virtual forest — collect and display all your grown trees
- [ ] 📊 Weekly/monthly analytics
- [ ] 🎨 Multiple tree themes (Cherry Blossom, Oak, Cactus...)
- [ ] 🤝 Friends & challenges — compete with friends
- [ ] 🌙 Deep Work Mode — block specific apps instead of all

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues, submit PRs, or suggest features.

```bash
# Fork the repo, then:
git checkout -b feature/your-feature-name
git commit -m "feat: add your feature"
git push origin feature/your-feature-name
# Open a Pull Request!
```

---

## 📜 License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute it.

---

<div align="center">

Made with ❤️ by **Ashutosh**

*"Your future is created by what you do today, not tomorrow."*

⭐ **Star this repo** if Atom Digital Detox helped you focus!

</div>
