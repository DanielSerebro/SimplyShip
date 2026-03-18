# Simply Ship - The Easy Unity Build Server

![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20Mac%20%7C%20Android%20%7C%20iOS-blue)

**Simply Ship** is a lightweight, portable, and automated build system designed to simplify the headache of Unity multi-platform deployments. It provides a clean web interface to manage headless builds across five major platforms simultaneously.

---

## 🚀 Key Features

- **Multi-Platform Support**: Built-in configurations for Windows, Linux, Mac, Android, and iOS.
- **Portable Executable**: No development environment required on your build machine. Just run the standalone `SimplyShip.exe`.
- **Headless Builds**: Fully automated builds using Unity's `-batchmode` and `-nographics`.
- **Parallel Processing**: Paid Feature: Kick off builds for multiple platforms at once.
- **Smart Zipping**: Automatic packaging of build artifacts with cross-platform extraction compatibility.
- **Live Logs**: Real-time log streaming from Unity directly to your browser (with multi-client syncing).
- **Validation**: Integrated folder and configuration checking to catch errors before you build.

---

## 🛠️ Setup Guide

### 1. How Simply Ship Works
Simply Ship automates **headless Unity builds**. Instead of opening Unity and switching platforms (which triggers slow asset re-imports), Simply Ship expects you to have a **separate cloned copy of your project for every platform** you intend to build. It then triggers Unity's command-line interface to build each of these projects in the background.

### 2. Organizing Your Folders
Choose a single directory on your machine to be your `PROJECTS_BASE_PATH`. Inside this folder, you should have a separate cloned git repository for each platform.

**Folder Naming Convention:**
Folders must be named as: `[ProjectName][Platform]` or `[ProjectName][Platform]Dev`
- **Windows:** `MyProjectWindows` & `MyProjectWindowsDev`
- **Linux:** `MyProjectLinux` & `MyProjectLinuxDev`
- **Android:** `MyProjectAndroid` & `MyProjectAndroidDev`

> **Note:** If the system cannot find a folder for a specific platform, it will simply ignore that platform during the build process.

### 3. Unity Build Profiles
Inside your Unity projects, you must use **Build Profiles** (the `.asset` files introduced in newer Unity versions). Simply Ship relies on these profiles to know exactly what scenes and settings to use.

**Profile Naming Requirements:**
The system looks for specific filenames inside your `BUILD_PROFILES_PATH`:
- **Production:** `Windows.asset`, `Linux.asset`, `Android.asset`, etc.
- **Development (-dev flag):</strong> `WindowsDev.asset`, `LinuxDev.asset`, `AndroidDev.asset`, etc.

### 4. Pre-Build Checklist
- **Switch Platforms:** Each project folder must already be set to its target platform in Unity. Simply Ship **will not** switch platforms for you.
- **Branch Management:** Each folder must be checked out to the git branch you want to build. Simply Ship **will not** change branches for you.
- **Validate:** Use the **"Validate All"** button on the Builder page to ensure your paths and Unity versions are correctly recognized before starting.

---

## 🔌 REST API

Simply Ship provides a simple REST endpoint to trigger builds from external tools or CI/CD pipelines.

### Trigger Build
- **Endpoint**: `POST /build`
- **Description**: Starts a build using the configuration and build arguments currently saved in `build_config.txt`.

**Example (cURL):**
```bash
curl -X POST http://localhost:3000/build
```

---

## ⚖️ Legal

&copy; Copyright Daniel Serebro 2026

**This project is not affiliated with, sponsored by, or endorsed by Unity Software Inc.** "Unity" is a registered trademark of Unity Software Inc.

Simply Ship is provided as-is without warranty of any kind.

---

Built with ❤️ for the Unity Community.
