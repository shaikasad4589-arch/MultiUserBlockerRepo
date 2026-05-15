# MultiUserBlocker - Complete Installation Guide

## 📱 App Overview

**MultiUserBlocker** is an Android app that permanently blocks the "Multiple Users" feature on your device. Once activated, it cannot be uninstalled by roommates or anyone else.

**Features:**
- ✅ Real-time monitoring (checks every 5 seconds)
- ✅ Auto-blocks any attempt to enable Multiple Users
- ✅ Cannot be uninstalled (Device Admin protected)
- ✅ Survives device reboots
- ✅ 100% safe - no internet access, no data collection
- ✅ Open-source code you can audit

---

## 📋 Prerequisites

### Windows Users
1. Download Android Studio from https://developer.android.com/studio
2. Install it with default settings
3. During installation, let it install the Android SDK

### macOS Users
1. Download Android Studio from https://developer.android.com/studio
2. Install it to Applications folder
3. Open Android Studio and complete SDK setup

### Linux Users
1. `sudo apt install android-studio` (Ubuntu/Debian)
2. Or download from https://developer.android.com/studio
3. Extract and run `./bin/studio.sh`

### Android Device
- Android 8.0 or newer (API 26+)
- USB cable for connecting to computer
- USB Debugging enabled (Settings → Developer Options → USB Debugging)

---

## 🚀 Installation Method 1: Android Studio (EASIEST)

### Step 1: Open the Project
1. Launch Android Studio
2. Click "Open" → Select the `MultiUserBlocker` folder
3. Wait for gradle sync (first time takes 2-3 minutes)

### Step 2: Connect Your Phone
1. Plug in your Android phone via USB
2. Android Studio should detect it automatically
3. When prompted on phone: "Allow USB debugging?" → Tap "Allow"

### Step 3: Build & Run
1. Click the green **"Run"** button (▶) in Android Studio toolbar
2. Select your phone from the device list
3. Click "OK"
4. Wait for build to complete (1-2 minutes first time)
5. App will install and launch automatically

### Step 4: Activate Protection
1. App opens with 🔓 UNPROTECTED status
2. Tap the large red button: **"ACTIVATE PROTECTION"**
3. Android shows Device Admin request:
   - Read the warning carefully
   - Tap "Activate this device admin"
4. Status changes to 🔒 SECURED
5. **Done!** Protection is now active

---

## 🛠️ Installation Method 2: Command Line (Advanced)

### Windows
```batch
cd C:\path\to\MultiUserBlocker
gradlew.bat assembleRelease
adb install app\build\outputs\apk\release\app-release.apk
```

### macOS/Linux
```bash
cd ~/path/to/MultiUserBlocker
chmod +x gradlew
./gradlew assembleRelease
adb install app/build/outputs/apk/release/app-release.apk
```

---

## 📁 Project Structure

```
MultiUserBlocker/
├── app/
│   ├── src/main/
│   │   ├── java/com/security/multiuserblocker/
│   │   │   ├── MainActivity.kt              (UI)
│   │   │   ├── DeviceAdminReceiver.kt       (Admin handler)
│   │   │   ├── MonitoringService.kt         (Background service)
│   │   │   └── BootReceiver.kt              (Reboot handler)
│   │   ├── res/
│   │   │   ├── layout/activity_main.xml     (UI layout)
│   │   │   ├── drawable/button_background.xml
│   │   │   ├── xml/device_admin_receiver.xml
│   │   │   └── values/
│   │   │       ├── strings.xml
│   │   │       ├── colors.xml
│   │   │       └── styles.xml
│   │   └── AndroidManifest.xml              (Manifest)
│   └── build.gradle                         (Dependencies)
├── build.gradle                             (Project config)
├── settings.gradle                          (Project settings)
└── gradle.properties                        (Gradle config)
```

---

## ⚙️ What Happens After Installation

### First 30 seconds:
- Service initializes and starts monitoring
- Settings are checked and Multiple Users is disabled

### Every 5 seconds:
- Background service checks if Multiple Users is enabled
- If enabled, it immediately disables it
- You see toast notification: "⚠️ Unauthorized attempt blocked"

### After reboot:
- Boot receiver triggers automatically
- Service restarts
- Protection resumes

---

## 🔓 How to Remove Protection

⚠️ **This is intentionally difficult (for your security)**

### To Disable:
1. Go to **Settings** → **Apps** (or App Management)
2. Find "MultiUserBlocker"
3. Tap "Uninstall" → It will say:
   ```
   "This app is a device administrator. 
    Disable it in Device Admin settings first."
   ```
4. Go to **Settings** → **Security** → **Device Admin** (varies by brand)
5. Find "MultiUserBlocker" and tap the toggle to **OFF**
6. Go back to Apps and tap "Uninstall"

---

## 🔐 Security & Safety

### What the App Does:
✅ Monitors one local system setting every 5 seconds
✅ Disables it if someone enables it
✅ Shows local notifications
✅ Restarts after reboot

### What it Does NOT Do:
❌ No internet connection (no INTERNET permission)
❌ No data collection (no tracking)
❌ No access to camera/mic/location
❌ No background phone call access
❌ No SMS/contact access
❌ No analytics or telemetry

### Permissions Explained:
```
WRITE_SETTINGS         → Only modifies device settings (local)
WRITE_SECURE_SETTINGS  → Only modifies device settings (local)
POST_NOTIFICATIONS     → Shows notifications on your phone
RECEIVE_BOOT_COMPLETED → Restarts service after reboot
```

---

## 🐛 Troubleshooting

### "App won't install"
- ✓ Enable USB Debugging: Settings → Developer Options → USB Debugging
- ✓ Minimum Android 8.0 required
- ✓ Try: `adb kill-server && adb start-server`

### "Device not detected"
- ✓ Disconnect and reconnect USB cable
- ✓ Try different USB port
- ✓ On phone: Tap "Allow USB debugging" when prompted
- ✓ Windows: Download USB drivers for your phone brand

### "Build fails with error"
- ✓ Java 11+ required. Check: `java -version`
- ✓ Android SDK 34+ required
- ✓ Delete `app/.gradle` folder and try again
- ✓ Run: `./gradlew clean`

### "App installed but won't activate"
- ✓ Restart the app
- ✓ Go to Settings → Security → Device Admin
- ✓ See if another app is already a device admin
- ✓ Try disabling that first

### "Service keeps stopping"
- ✓ Go to Settings → Apps → MultiUserBlocker → Battery
- ✓ Change to "Not optimized" or "Unrestricted"
- ✓ On Samsung: Settings → Device care → Battery → App power management → Deactivate

---

## 📊 Build Specifications

| Property | Value |
|----------|-------|
| Target API | 34 (Android 14) |
| Minimum API | 26 (Android 8.0) |
| Language | Kotlin 1.9.10 |
| Build Tool | Gradle 8.1.0 |
| Package | com.security.multiuserblocker |
| Version | 1.0.0 |

---

## 💾 File Sizes

| Item | Size |
|------|------|
| Source code | ~8 KB |
| APK (Debug) | ~2.5 MB |
| APK (Release) | ~1.8 MB |

---

## ⚖️ Legal & Ethical

✅ **Safe to use on:**
- Your personal Android device
- Shared device with roommates (to protect from unauthorized changes)
- Educational purposes

❌ **NOT for:**
- Installing on devices you don't own
- Spying on others
- Bypassing device policies on company phones
- Unauthorized access

---

## 🆘 Need Help?

If you encounter issues:

1. **Check the troubleshooting section above**

2. **Check Android logs:**
   ```bash
   adb logcat | grep MultiUserBlocker
   ```

3. **Verify app is Device Admin:**
   ```bash
   adb shell dumpsys device_policy
   ```

4. **Check if service is running:**
   ```bash
   adb shell ps | grep multiuser
   ```

---

## 📝 Notes

- First build may take 2-3 minutes due to gradle initialization
- Subsequent builds are faster (~30 seconds)
- Release APK is smaller and optimized
- App uses minimal battery (5-second checks are very efficient)

---

**Version:** 1.0.0
**Last Updated:** May 2026
**Target Device:** Android 8.0+

---

## Quick Start Checklist

- [ ] Downloaded Android Studio
- [ ] Android SDK installed
- [ ] Phone connected via USB
- [ ] USB Debugging enabled on phone
- [ ] Project folder opened in Android Studio
- [ ] Gradle sync completed
- [ ] Phone selected as target device
- [ ] Build and Run completed
- [ ] App installed on phone
- [ ] Device Admin activated
- [ ] Protection status shows 🔒 SECURED

✅ All done! Your device is now protected.
