# adbTrimboost

**adbTrimboost** is a real, **non-root fstrim utility** for Android that boosts storage performance by safely triggering Android’s internal trim operation. Designed for advanced users, this APK-based solution utilizes Android’s native mechanisms to reclaim unused flash storage blocks—without requiring root access.

---

## ⚡ What Is fstrim?

`fstrim` informs the storage controller of unused blocks, allowing the system to optimize wear leveling and performance on flash-based storage (eMMC/UFS). On Android, this typically happens automatically, but many devices delay or disable it due to aggressive power management or OEM restrictions.

---

## 🚀 What Does adbTrimboost Do?

Android internally uses a system-level parameter (`fstrim_mandatory_interval`) to control when fstrim should be executed. **adbTrimboost**:

- Leverages this mechanism to **trigger an fstrim safely**
- Works **without root**
- Uses only standard Android APIs
- Can be initiated via ADB or in-app execution
- Helps reclaim performance on neglected or poorly maintained devices

---

## 🔍 How It Works

The core logic uses Android’s PackageManagerService to manipulate the `fstrim_mandatory_interval`, effectively forcing the system to schedule and run a trim operation immediately.

Reference:
- [Android Source: PackageManagerService.java](https://cs.android.com/android/platform/superproject/+/master:frameworks/base/services/core/java/com/android/server/pm/PackageManagerService.java;l=9636?q=fstrim_mandatory_interval)

This keeps the trim operation **within Android’s official system behavior** and avoids unsafe hacks or root requirements.

---

## 📦 APK Details

- **App Name**: adbTrimboost
- **Package**: `com.yash.trimboost`
- **Root Required**: ❌ No

---

## 📲 Installation

1. Download the latest APK from the [Releases](https://github.com/yashyc7/mFSTRIM/releases)
2. Enable “Install from Unknown Sources” in Android settings
3. Install the APK
4. Launch and run trim operation (or use via ADB)
