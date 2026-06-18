# ClockUp for Android

Public download host for the **ClockUp** Android app — WebOuts' internal video-production pipeline tool. This repo contains **only release APK files** (no source code; the source lives in the private WebOuts monorepo).

## 📥 Download / Install

**Always-newest link:** https://github.com/TKsmalls/clockup-app/releases/latest/download/clockup.apk

This link always serves the latest version, so the download button on webouts.com points here once and never needs changing.

**Installing on an Android phone:**
1. Open the link above on the phone.
2. Open the downloaded `clockup.apk`.
3. Android shows a one-time "install from this source?" prompt → allow it → **Install**.
4. Open ClockUp and sign in with your WebOuts email.

## 🔄 Updates

- **Most updates are automatic (over-the-air):** just reopen the app — it updates itself, no re-downloading.
- **Occasional larger ("native") updates** need a fresh APK, published here as a new release. The link above auto-serves the newest one.

## Maintainer notes

**Over-the-air update (JS/UI/logic changes — the common case):**
```
eas update --branch production --message "what changed"
```
Reaches all installed apps automatically on next launch. No new APK, no website change.

**Full APK release (native change — new Expo SDK, permissions, icon, etc.):**
```
eas build --platform android --profile preview
# download the .apk, rename it to clockup.apk, then:
gh release create vX.Y.Z clockup.apk --repo TKsmalls/clockup-app --title "ClockUp X.Y.Z" --notes "what changed"
```
