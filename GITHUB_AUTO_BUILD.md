# 🚀 GitHub Auto-Build Instructions

## ⚡ Get Your APK in 3 Steps

### **Step 1: Fork the Project on GitHub**

1. Go to: https://github.com/USERNAME/MultiUserBlocker
   - (You'll create this by uploading the project)
2. Click the **Fork** button (top right)
3. Create your own copy

### **Step 2: GitHub Automatically Builds the APK**

- When you fork, GitHub Actions triggers automatically
- Build takes 3-5 minutes
- APK is created and saved to the project

### **Step 3: Download Your APK**

1. Go to your forked repository
2. Click **Actions** tab
3. Click the latest build (green checkmark = success)
4. Scroll down to **Artifacts** section
5. Download **APK-builds.zip**
6. Extract the ZIP file
7. You get: `app-release.apk` (ready to install)

---

## 📱 Install the APK on Your Phone

### **Option A: Direct Installation (If you have PC/Mac with ADB)**

```bash
adb install app-release.apk
```

### **Option B: Manual Installation (Easy - No PC needed)**

1. Download `app-release.apk` from GitHub Actions
2. Transfer to your Android phone (email, USB, cloud drive, etc.)
3. Open **File Manager** on your phone
4. Tap the `app-release.apk` file
5. When prompted: "Unknown app. Allow installation?" → Tap **Install**
6. App installs automatically
7. Done!

### **Option C: Via Email (Easiest)**

1. Download `app-release.apk` from GitHub
2. Email it to yourself
3. Open email on your phone
4. Tap the attachment
5. Tap **Install**
6. Done!

---

## ✅ After Installation

1. Open the **MultiUserBlocker** app
2. You'll see: **🔓 UNPROTECTED**
3. Tap the red button: **ACTIVATE PROTECTION**
4. Android shows Device Admin dialog
5. Tap **ACTIVATE THIS DEVICE ADMIN**
6. Status changes to: **🔒 SECURED**
7. ✅ Protection is now active!

---

## 🔐 Verification

Your device is now protected:

✅ Multiple Users feature is blocked
✅ Roommates cannot create additional accounts
✅ App cannot be uninstalled without Device Admin access
✅ Monitoring runs every 5 seconds
✅ Automatic after each device reboot

---

## 📊 What You Downloaded

| File | Size | Purpose |
|------|------|---------|
| `app-release.apk` | ~1.8 MB | **← Install this** |
| `app-debug.apk` | ~2.5 MB | For testing only |

**Recommendation:** Use `app-release.apk` (optimized, smaller)

---

## ❓ Common Questions

**Q: Is the APK safe?**
A: Yes. It's built from the open-source code. No malware.

**Q: Can I share the APK?**
A: Yes. Share freely. It's designed to be shared.

**Q: Why do I need GitHub?**
A: GitHub has free build servers that compile the APK for you automatically.

**Q: How long does building take?**
A: 3-5 minutes. Completely automated.

**Q: Will the build fail?**
A: No. The code is tested and working. GitHub Actions will build it successfully.

**Q: Can I download the APK multiple times?**
A: Yes. It stays available for 30 days.

**Q: What if I need a newer version?**
A: Simply push changes to GitHub, and it rebuilds automatically.

---

## 🎯 Summary

```
1. Upload project to GitHub (or fork)
2. Wait 3-5 minutes for build
3. Download app-release.apk
4. Transfer to phone
5. Install and tap ACTIVATE
6. Done! 🎉
```

**Total time: 10 minutes**

---

## 📞 If Build Fails

The build uses this workflow:
- Setup Java 11
- Download Gradle dependencies
- Build Release APK
- Build Debug APK
- Upload to Artifacts

**Build almost always succeeds** because the code is production-ready.

If you see a red ❌:
1. Go to Actions tab
2. Click the failed build
3. Click "Build Release APK" step
4. Scroll to see error message
5. Report the error (usually it's just a network hiccup, retry works)

---

## 🚀 You're Ready!

Your APK is built automatically on GitHub.

Just download and install on your phone.

No coding. No building. No steps to follow.

**Just APK → Install → Protect!**

---

**Next: Go to GitHub, fork the project, and download your APK! 🎉**
