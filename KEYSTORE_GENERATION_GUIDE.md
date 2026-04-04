# 🔐 CricApp - Release Keystore Generation Guide

## यह Document क्यों Important है?

Play Store पर app upload करने के लिए **Release Keystore** ज़रूरी है। यह आपकी app की digital signature है।

⚠️ **CRITICAL WARNING:**
- Keystore file और passwords **KABHI मत खोना**
- इसके बिना app update **IMPOSSIBLE** है
- Multiple जगहों पर backup रखो (Google Drive, USB, Email)

---

## 📋 Step-by-Step Guide

### Step 1: Terminal/Command Prompt खोलो

**Windows:**
- Start Menu → "cmd" search करो → Enter

**Mac/Linux:**
- Terminal app खोलो

---

### Step 2: Keystore Generate करो

नीचे का command copy करके paste करो:

```bash
keytool -genkey -v -keystore cricapp-release.keystore -alias cricapp -keyalg RSA -keysize 2048 -validity 10000
```

---

### Step 3: Information Fill करो

Command run करने पर यह questions आएंगे:

```
Enter keystore password: [अपना password डालो - याद रखना!]
Re-enter new password: [same password फिर से]

What is your first and last name?
  [Unknown]: GemmiApps

What is the name of your organizational unit?
  [Unknown]: Mobile Development

What is the name of your organization?
  [Unknown]: GemmiApps

What is the name of your City or Locality?
  [Unknown]: [अपना city]

What is the name of your State or Province?
  [Unknown]: [अपना state]

What is the two-letter country code for this unit?
  [Unknown]: IN

Is CN=GemmiApps, OU=Mobile Development, O=GemmiApps, L=[City], ST=[State], C=IN correct?
  [no]: yes
```

---

### Step 4: Key Password Set करो

```
Enter key password for <cricapp>
  (RETURN if same as keystore password): [Enter दबाओ या different password]
```

---

### Step 5: Verify Keystore Created

```bash
# Check if file created
ls -la cricapp-release.keystore

# View keystore details
keytool -list -v -keystore cricapp-release.keystore
```

---

## 📁 Generated Files & Info को Save करो

### ✅ इन्हें SECURELY SAVE करो:

| Item | Value | Save Location |
|------|-------|---------------|
| **Keystore File** | `cricapp-release.keystore` | Google Drive + USB + Computer |
| **Keystore Password** | [जो आपने set किया] | Password Manager / Secure Note |
| **Key Alias** | `cricapp` | Same as above |
| **Key Password** | [जो आपने set किया] | Same as above |
| **Validity** | 10000 days (~27 years) | - |

---

## 🔧 Android Project में Configure करो

### Step 1: Keystore file copy करो

```bash
# Keystore को android/app folder में copy करो
cp cricapp-release.keystore /path/to/CricApp/frontend/android/app/
```

### Step 2: `gradle.properties` में add करो

File: `/frontend/android/gradle.properties`

Add these lines at the end:

```properties
# Release Keystore Configuration
CRICAPP_UPLOAD_STORE_FILE=cricapp-release.keystore
CRICAPP_UPLOAD_KEY_ALIAS=cricapp
CRICAPP_UPLOAD_STORE_PASSWORD=your_keystore_password_here
CRICAPP_UPLOAD_KEY_PASSWORD=your_key_password_here
```

⚠️ **Replace** `your_keystore_password_here` और `your_key_password_here` with actual passwords!

### Step 3: `build.gradle` में signingConfigs update करो

File: `/frontend/android/app/build.gradle`

Find `signingConfigs` section and update:

```gradle
android {
    ...
    signingConfigs {
        debug {
            storeFile file('debug.keystore')
            storePassword 'android'
            keyAlias 'androiddebugkey'
            keyPassword 'android'
        }
        release {
            if (project.hasProperty('CRICAPP_UPLOAD_STORE_FILE')) {
                storeFile file(CRICAPP_UPLOAD_STORE_FILE)
                storePassword CRICAPP_UPLOAD_STORE_PASSWORD
                keyAlias CRICAPP_UPLOAD_KEY_ALIAS
                keyPassword CRICAPP_UPLOAD_KEY_PASSWORD
            }
        }
    }
    buildTypes {
        debug {
            signingConfig signingConfigs.debug
        }
        release {
            signingConfig signingConfigs.release
            minifyEnabled true
            shrinkResources true
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
}
```

---

## 🚀 Build Release APK/AAB

### Option 1: Local Build

```bash
cd frontend/android

# Build Release APK
./gradlew assembleRelease

# Build Release AAB (for Play Store)
./gradlew bundleRelease
```

### Option 2: GitHub Actions (Already Configured)

Push to GitHub → Auto build triggers

---

## 📍 Output File Locations

| Build Type | Location |
|------------|----------|
| **Release APK** | `frontend/android/app/build/outputs/apk/release/app-release.apk` |
| **Release AAB** | `frontend/android/app/build/outputs/bundle/release/app-release.aab` |

---

## ✅ Verification Checklist

- [ ] Keystore file generated: `cricapp-release.keystore`
- [ ] Keystore password saved securely
- [ ] Key alias noted: `cricapp`
- [ ] Key password saved securely
- [ ] Keystore backed up to Google Drive
- [ ] Keystore backed up to USB/External drive
- [ ] gradle.properties updated
- [ ] build.gradle updated
- [ ] Test build successful

---

## 🆘 Common Errors & Solutions

### Error: "keytool not found"
```bash
# Windows: Add Java to PATH
set PATH=%PATH%;C:\Program Files\Java\jdk-17\bin

# Mac: Install Java
brew install openjdk@17
```

### Error: "keystore was tampered with"
- Password गलत है, सही password डालो

### Error: "alias does not exist"
- Key alias check करो: `cricapp`

---

## 📞 Important Notes

1. **Play Store Upload के बाद:**
   - Same keystore से ही updates होंगी
   - Different keystore = New app (पुराना update नहीं होगा)

2. **Google Play App Signing:**
   - Play Console में App Signing enable करो
   - Google आपकी key का backup रखता है
   - Recommended for extra safety

3. **Keystore Backup Locations:**
   - Google Drive (encrypted folder)
   - USB Drive (secure location)
   - Email to yourself (password protected zip)
   - Password Manager

---

*Document Version: 1.0*
*For: CricApp (com.cricapp.live)*
*Created: April 2026*
