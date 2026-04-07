# 🔐 CricApp - Release Keystore Information
# ⚠️ IMPORTANT: इस फाइल को SAFE रखो! कभी DELETE मत करना!

---

## 📋 KEYSTORE DETAILS (हमेशा याद रखो)

| Property | Value |
|----------|-------|
| **Keystore File** | `release-keystore.jks` |
| **Keystore Password** | `CricApp2026Release` |
| **Key Alias** | `cricapp-release` |
| **Key Password** | `CricApp2026Release` |
| **Validity** | 10,000 days (~27 years) |
| **Algorithm** | RSA 2048-bit |

---

## ⚠️ IMPORTANT WARNINGS:

### 1. KEYSTORE FILE DOWNLOAD करो!
- GitHub Actions के Artifacts से `CricApp-Release-Keystore` download करो
- इसे अपने computer में SAFE जगह save करो
- Multiple backups रखो (Google Drive, USB, etc.)

### 2. अगर KEYSTORE खो गया तो:
- ❌ App को UPDATE नहीं कर पाओगे
- ❌ नई app बनानी पड़ेगी (different package name)
- ❌ सारे existing users lost हो जाएंगे

### 3. PASSWORD कभी SHARE मत करो:
- Keystore password secret रखो
- कहीं public मत डालो

---

## 🔄 Future Updates के लिए:

जब भी नया AAB build करो, same keystore use होगा automatically.

अगर manually build करना हो:
```bash
cd frontend/android
./gradlew bundleRelease \
  -PRELEASE_STORE_FILE=app/release-keystore.jks \
  -PRELEASE_STORE_PASSWORD=CricApp2026Release \
  -PRELEASE_KEY_ALIAS=cricapp-release \
  -PRELEASE_KEY_PASSWORD=CricApp2026Release
```

---

## 📱 Play Store Upload के बाद:

Play Console में जाकर:
1. Release > Setup > App signing
2. "App signing certificate" section देखो
3. SHA-1 और SHA-256 fingerprints note करो (APIs के लिए)

---

**Created:** April 2026
**App:** CricApp
**Package:** com.cricapp.live
