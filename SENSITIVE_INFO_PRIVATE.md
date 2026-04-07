# 🔐 CricApp - Sensitive Information

---

## 📱 Test Device Advertising ID

**File:** `frontend/src/context/AdMobContext.native.tsx`
**Line:** 148

**Current Value:**
```typescript
testDeviceIdentifiers: ['553c7721-4821-461b-9f62-8584b1e60745'],
```

**This is YOUR phone's Advertising ID**

---

## ⚠️ IMPORTANT:

### During Testing (14 days):
- **KEEP this ID** in the code
- Your phone will show TEST ads (not real ads)
- This prevents accidental clicks on real ads (which can get you banned)

### For Production Release (After 14 days):
- **REMOVE this ID** or make it empty
- Change to:
```typescript
testDeviceIdentifiers: [],
```

---

## 🔑 Keystore Info (Also save this):

| Property | Value |
|----------|-------|
| File | release-keystore.jks |
| Password | CricApp2026Release |
| Alias | cricapp-release |
| Key Password | CricApp2026Release |

---

**Keep this file SAFE and PRIVATE!**
