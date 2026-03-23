# Simply Ship - The Easy Unity Build Server

![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20Mac%20%7C%20Android%20%7C%20iOS-blue)

**Simply Ship** is a lightweight, portable, and automated build system designed to simplify the headache of Unity multi-platform deployments. It provides a clean web interface to manage headless builds across five major platforms simultaneously.

![Simply Ship Preview](SimplyShipImage.png)

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

## 🚀 Quick Start Guide

Simply Ship automates headless Unity builds. Instead of opening Unity and switching platforms (which triggers slow asset re-imports), Simply Ship expects you to have a cloned copy of your project for every platform you intend to build. It then triggers Unity's command-line interface to build each of these projects in the background.

### 1. How it Works
Simply Ship leverages Unity's command-line interface to trigger builds in the background across multiple project clones, ensuring you never have to wait for platform switching again.

### 2. Organizing Your Folders
Choose a single directory on your machine to be your `PROJECTS_BASE_PATH`. Inside this folder, you should have a separate cloned git repository for each platform.

#### Folder Naming Convention
Folders must be named as: `[ProjectName][Platform]` or `[ProjectName][Platform]Dev`

- **Windows**: `SpookerWindows` & `SpookerWindowsDev`
- **Linux**: `SpookerLinux` & `SpookerLinuxDev`
- **Android**: `SpookerAndroid` & `SpookerAndroidDev`

**Automatic Skipping:**
If the system cannot find a folder for a specific platform (e.g., `SpookerMac` is missing), it will simply ignore that platform during the build process.

### 3. Unity Build Profiles
Inside your Unity projects, you must use **Build Profiles** (the `.asset` files introduced in newer Unity versions). Simply Ship relies on these profiles to know exactly what scenes and settings to use.

#### Profile Naming Requirements
The system looks for specific filenames inside your `BUILD_PROFILES_PATH`:

- **Production**: `Windows.asset`, `Linux.asset`, `Android.asset`, etc.
- **Development** (`-dev` flag): `WindowsDev.asset`, `LinuxDev.asset`, `AndroidDev.asset`, etc.

*Note: The "Windows", "Linux" etc. parts are defined by your `PROFILE_NAME_XXX` settings in the config.*

### 4. Pre-Build Checklist
- **Switch Platforms**: Each project folder must already be set to its target platform in Unity. Simply Ship will not switch platforms for you.
- **Branch Management**: Each folder must be checked out to the git branch you want to build. Simply Ship will not change branches for you.
- **Validate**: Use the **"Validate All"** button on the Builder page to ensure your paths and Unity versions are correctly recognized before starting.

### 5. REST API (Remote Trigger)
You can trigger a build from a script or CI/CD pipeline by sending a POST request. It will use the settings currently saved in your config file.

```bash
curl -X POST http://localhost:3000/build
```

**Monitoring**: The API returns immediately. You can monitor progress by keeping the web UI open (it will sync automatically) or by checking `build.log`.

---

## ⚖️ Legal

&copy; Copyright Daniel Serebro 2026

**This project is not affiliated with, sponsored by, or endorsed by Unity Software Inc.** "Unity" is a registered trademark of Unity Software Inc.

Simply Ship is provided as-is without warranty of any kind.

---

Built with ❤️ for the Unity Community.
