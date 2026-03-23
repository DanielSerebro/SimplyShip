# Simply Ship - The Easy Unity Build Server

![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20Mac%20%7C%20Android%20%7C%20iOS-blue)

**Simply Ship** is a lightweight, portable, and automated build system designed to simplify the headache of Unity multi-platform deployments. It provides a clean web interface to manage headless builds across five major platforms simultaneously.

---

## 🚀 Key Features

- **Multi-Platform Support**: Built-in configurations for Windows, Linux, Mac, Android, and iOS.
- **Portable Executable**: No development environment required on your build machine. Just run the standalone `SimplyShip.exe`.
- **Headless Builds**: Fully automated builds using Unity's `-batchmode` and `-nographics`.
- **Parallel Processing**: Kick off builds for multiple platforms at once.
- **Smart Zipping**: Automatic packaging of build artifacts with cross-platform extraction compatibility.
- **Live Logs**: Real-time log streaming from Unity directly to your browser.
- **Validation**: Integrated folder and configuration checking to catch errors before you build.

---

## 💰 Pricing

Simply Ship is free for personal use. Premium features are available for commercial teams.

| Feature | Free | Premium | Enterprise |
| :--- | :---: | :---: | :---: |
| Win/Mac/Linux/Android/iOS | ✔ | ✔ | ✔ |
| Dev & Clean Builds | ✔ | ✔ | ✔ |
| Logs & Remote Trigger | ✔ | ✔ | ✔ |
| **Parallel Build Support** | ✘ | ✔ | ✔ |
| **Eligibility** | Personal | Teams < $250k & < 50 size | Teams ≥ $250k or ≥ 50 size |
| **Price** | **Free** | **$50 AUD (One-off)** | **Contact Us** |
| | | [**Buy Now**](https://danthedev.lemonsqueezy.com/checkout) | [**Buy Now**](https://danthedev.lemonsqueezy.com/checkout) |

---

## 🛠️ Quick Start

### 1. Prerequisites
- **Unity Hub & Editors**: Installed at the path specified in your config.
- **Git**: Installed and accessible via command line.
- **Project Structure**: We recommend having separate directories for each platform (e.g., `MyProjectWindows`, `MyProjectAndroid`) to avoid slow asset re-imports.

### 2. Setup
1. Download the latest `SimplyShip` executable for your platform.
2. Place it in a folder of your choice.
3. Run the executable. A default `build_config.txt` will be created automatically in the same directory.

### 3. Usage
1. Open `http://localhost:3000` in your browser.
2. Use the **Project Configuration** section to set your Unity version, project name, and paths.
3. Use the **Build Arguments** to toggle zipping, ignoring platforms, or parallel mode.
4. Click **Start Build Process** and watch the magic happen.

---

## 📂 Expected Directory Layout

To maximize build speed, Simply Ship expects separate project folders per platform:

- `PROJECTS_BASE_PATH/`
  - `ProjectNameWindows/`
  - `ProjectNameLinux/`
  - `ProjectNameAndroid/`
  - ... (and so on)

---

## ⚖️ Legal

&copy; Copyright Daniel Serebro 2026

**This project is not affiliated with, sponsored by, or endorsed by Unity Software Inc.** "Unity" is a registered trademark of Unity Software Inc.

Simply Ship is provided as-is without warranty of any kind.

---

Built with ❤️ for the Unity Community.
