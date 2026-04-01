# 🏏 CricApp - COMPLETE IDs, KEYS & DETAILS REFERENCE

---

## 📱 APP IDENTITY (FULL DETAILS)

| Property | Value | Notes |
|----------|-------|-------|
| **App Name** | `CricApp` | Display name on device |
| **Slug** | `cric-app` | Expo project slug |
| **Package Name (Android)** | `com.cricapp.live` | ⚠️ NEVER CHANGE after Play Store upload |
| **Scheme** | `cricapp` | Deep linking scheme (cricapp://) |
| **Version** | `1.0.1` | User visible version |
| **Owner** | `gemmiapps` | Expo account owner |
| **Developer** | `GemmiApps` | Shown in About page |

---

## 🔑 RAPIDAPI KEYS (CRICBUZZ DATA) - FULL LIST

### API Providers:
| Provider | Base URL | Host |
|----------|----------|------|
| Primary | `https://cricbuzz-cricket.p.rapidapi.com` | `cricbuzz-cricket.p.rapidapi.com` |
| Fallback | `https://cricbuzz.p.rapidapi.com` | `cricbuzz.p.rapidapi.com` |

### All 10 API Keys:

| Key # | RapidAPI Key | Check Status |
|-------|--------------|--------------|
| 1 | `90023f4cffmsh601a9c68cd49cc7p181c2ajsn5bc8b2d875fc` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 2 | `d5dc9c8512mshe9bec708eb2b011p14ac97jsn4a79d9ec6dc4` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 3 | `7a2524853emsh5f7b21ec1386710p17ba7djsn8c535a072237` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 4 | `59b9249be3mshcab753fe794baa3p14e78cjsne1da55eef3aa` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 5 | `c651c7e717msh7d7c4d05cae7b6dp17500bjsn1e00d9cf8d61` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 6 | `2a21f65881msh680271f280de7p182fbdjsn151d068c6392` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 7 | `cd6ae88bddmsh5dcf84f0286d14cp1af3f9jsn7d2de7fe2a03` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 8 | `4223543bdbmsh7962a0ecb8d4e7fp1132a3jsn8f9a656e2b32` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 9 | `ba8052cb25msh6ea2297ebf719dcp14bc6ejsn51e281c87482` | [Check Limit](https://rapidapi.com/developer/dashboard) |
| 10 | `db67e8004emsh40add8626f58e58p183678jsne28298b94c3b` | [Check Limit](https://rapidapi.com/developer/dashboard) |

### Key Rotation Logic:
- Auto-rotates on HTTP 429 (Rate Limit Exceeded)
- Auto-rotates on HTTP 403 (Forbidden/Key Invalid)
- Server-side cache: **3 minutes** (reduces API calls)

### RapidAPI Dashboard:
- **URL:** https://rapidapi.com/developer/dashboard
- **API Used:** Cricbuzz Cricket API
- **Free Tier:** Usually 100-500 requests/month per key

---

## 💰 ADMOB IDs (GOOGLE ADS) - FULL LIST

### AdMob Account:
| Property | Value |
|----------|-------|
| **Publisher ID** | `pub-9675798593675825` |
| **AdMob Console** | https://admob.google.com/ |

### Android App IDs:

| Ad Type | Ad Unit ID | Usage |
|---------|-----------|-------|
| **App ID** | `ca-app-pub-9675798593675825~2399929714` | Main app identifier |
| **App Open Ad** | `ca-app-pub-9675798593675825/4826782503` | Shows on app launch (all users) |
| **Interstitial Ad** | `ca-app-pub-9675798593675825/8438724452` | Full-screen ad (non-Pro users, every 10-15 clicks) |
| **Banner Ad** | `ca-app-pub-9675798593675825/8616886104` | Commentary section (all users, every 2 balls) |
| **Rewarded Ad** | `ca-app-pub-9675798593675825/6702740458` | Watch 3 ads to unlock Pro (30 min) |

### iOS App IDs (Test/Placeholder):
| Ad Type | Ad Unit ID | Notes |
|---------|-----------|-------|
| **iOS App ID** | `ca-app-pub-3940256099942544~1458002511` | Google test ID (not real) |

### Test Device ID:
| Property | Value |
|----------|-------|
| **Test Device ID** | `553c7721-4821-461b-9f62-8584b1e60745` | Your device for testing ads |

### Ad Configuration in Code:
**File:** `/app/frontend/src/context/AdMobContext.native.tsx`
```javascript
const AD_UNIT_IDS = {
  appOpen: 'ca-app-pub-9675798593675825/4826782503',
  interstitial: 'ca-app-pub-9675798593675825/8438724452',
  banner: 'ca-app-pub-9675798593675825/8616886104',
  rewarded: 'ca-app-pub-9675798593675825/6702740458',
};
```

---

## 🆔 ALL OTHER IDs & IDENTIFIERS

### Expo/EAS:
| Property | Value | Purpose |
|----------|-------|---------|
| **EAS Project ID** | `47d65cb3-f161-4591-bbd9-9d062e96ca5d` | Expo build service |
| **Expo Username** | `Vinu2092` | Expo account login |
| **Expo Password** | `Vinod2092@` | Expo account password |
| **Expo Dashboard** | https://expo.dev/accounts/Vinu2092/projects/cricapp | Build status |

### Android Notification Channels:
| Channel ID | Name | Purpose |
|------------|------|---------|
| `floating_widget_channel` | Floating Score Widget | Foreground service notification |

### Deep Link Schemes:
| Scheme | Example | Purpose |
|--------|---------|---------|
| `cricapp://` | `cricapp://match/123` | Open app from external link |
| `com.cricapp.live://` | Auto-generated | Package-based scheme |

---

## 👤 DEVELOPER & ACCOUNT DETAILS

### Developer Info:
| Property | Value |
|----------|-------|
| **Developer Name** | `GemmiApps` |
| **Shown in App** | About page: "Developed by GemmiApps" |
| **Copyright** | © 2026 CricApp. All rights reserved. |

### Expo Account:
| Property | Value |
|----------|-------|
| **Username** | `Vinu2092` |
| **Password** | `Vinod2092@` |
| **Dashboard** | https://expo.dev |
| **Project URL** | https://expo.dev/accounts/Vinu2092/projects/cricapp |

### GitHub Repository:
| Property | Value |
|----------|-------|
| **Repo URL** | https://github.com/gemmiapps-rgb/CricApp.git |
| **Branch** | `main` |
| **Actions** | Auto-build on push |

---

## 📁 KEY FILE LOCATIONS

| File | Purpose | Location |
|------|---------|----------|
| **AdMob Config** | Ad unit IDs | `/app/frontend/src/context/AdMobContext.native.tsx` |
| **App Config** | Package name, version | `/app/frontend/app.json` |
| **API Keys** | RapidAPI keys | `/app/backend/server.py` |
| **Android Manifest** | Permissions, package | `/app/frontend/android/app/src/main/AndroidManifest.xml` |
| **Build Gradle** | Signing, build config | `/app/frontend/android/app/build.gradle` |
| **Floating Widget** | Native overlay code | `/app/frontend/android/app/src/main/java/com/cricapp/live/floatingwidget/` |
| **Splash Screen** | Custom splash | `/app/frontend/src/components/SplashScreen.tsx` |
| **Pro Context** | Pro user logic | `/app/frontend/src/context/ProContext.tsx` |

---

## 🔐 SIGNING & SECURITY

### Current Keystore (DEBUG - Not for Production!):
| Property | Value |
|----------|-------|
| **File** | `/app/frontend/android/app/debug.keystore` |
| **Type** | Debug (auto-generated) |
| **Use** | Development only |

### For Production Release:
```bash
# Generate release keystore (RUN THIS BEFORE PLAY STORE UPLOAD)
keytool -genkey -v -keystore cricapp-release.keystore -alias cricapp -keyalg RSA -keysize 2048 -validity 10000

# You'll be asked for:
# - Keystore password (remember this!)
# - Key password (can be same)
# - Name, Organization, etc.
```

### ⚠️ CRITICAL: Save These Securely!
After generating keystore, save:
1. `cricapp-release.keystore` file
2. Keystore password
3. Key alias: `cricapp`
4. Key password

**If you lose these, you can NEVER update the app on Play Store!**

---

## 📊 QUICK REFERENCE CARD

### Copy-Paste Ready:

```
=== APP ===
Package: com.cricapp.live
Version: 1.0.1

=== ADMOB ===
App ID: ca-app-pub-9675798593675825~2399929714
App Open: ca-app-pub-9675798593675825/4826782503
Interstitial: ca-app-pub-9675798593675825/8438724452
Banner: ca-app-pub-9675798593675825/8616886104
Rewarded: ca-app-pub-9675798593675825/6702740458
Test Device: 553c7721-4821-461b-9f62-8584b1e60745

=== RAPIDAPI KEYS ===
Key 1: 90023f4cffmsh601a9c68cd49cc7p181c2ajsn5bc8b2d875fc
Key 2: d5dc9c8512mshe9bec708eb2b011p14ac97jsn4a79d9ec6dc4
Key 3: 7a2524853emsh5f7b21ec1386710p17ba7djsn8c535a072237
Key 4: 59b9249be3mshcab753fe794baa3p14e78cjsne1da55eef3aa
Key 5: c651c7e717msh7d7c4d05cae7b6dp17500bjsn1e00d9cf8d61
Key 6: 2a21f65881msh680271f280de7p182fbdjsn151d068c6392
Key 7: cd6ae88bddmsh5dcf84f0286d14cp1af3f9jsn7d2de7fe2a03
Key 8: 4223543bdbmsh7962a0ecb8d4e7fp1132a3jsn8f9a656e2b32
Key 9: ba8052cb25msh6ea2297ebf719dcp14bc6ejsn51e281c87482
Key 10: db67e8004emsh40add8626f58e58p183678jsne28298b94c3b

=== EXPO ===
Project ID: 47d65cb3-f161-4591-bbd9-9d062e96ca5d
Username: Vinu2092
Password: Vinod2092@

=== DEVELOPER ===
Name: GemmiApps
GitHub: github.com/gemmiapps-rgb/CricApp
```

---

## 🔗 IMPORTANT URLS

| Service | URL |
|---------|-----|
| **AdMob Console** | https://admob.google.com/ |
| **RapidAPI Dashboard** | https://rapidapi.com/developer/dashboard |
| **Expo Dashboard** | https://expo.dev/accounts/Vinu2092/projects/cricapp |
| **Play Console** | https://play.google.com/console |
| **GitHub Repo** | https://github.com/gemmiapps-rgb/CricApp |
| **GitHub Actions** | https://github.com/gemmiapps-rgb/CricApp/actions |

---

*Document Created: April 2026*
*Version: 2.0 (Complete)*
