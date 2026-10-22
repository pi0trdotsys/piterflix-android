# Piterflix for Android

Piterflix is an Android client for a self-hosted Jellyfin server. It is based on
[Findroid](https://github.com/jarnedemeulemeester/findroid), commit
`f7d090f7814c7aa6e1e19fe319fe15f4e6e01ce4`, under GPL-3.0. The original
license is preserved in `LICENSE`. This source archive contains the complete
corresponding source for the Piterflix APK built from this tree.

The app is identified as `eu.prosinski.piterflix`, so it can coexist with
Findroid. It uses Piterflix branding, a red and charcoal palette, a dark
default theme, a cinematic home feature, and tighter corners across the app.
Jellyfin playback, downloads, and offline mode come from Findroid.

## Build

Install Android SDK with API 37 and Build Tools 37.0.0, JDK 17, and set
`ANDROID_HOME` and `JAVA_HOME`. On Windows:

```powershell
.\gradlew.bat :app:phone:assembleLibreDebug
```

The APKs appear under `app/phone/build/outputs/apk/libre/debug/`.
The debug APK is test-signed by the local Android debug key. A production
release needs its own persistent release signing key.

## Offline use

Sign in to the Jellyfin server, download a movie or an episode from its detail
screen, and open **Pobrane / Downloads**. To watch when the server is unreachable,
turn on **Tryb offline / Offline mode** in settings. Findroid downloads original
media and plays it directly; device codec support matters. Its upstream README
specifies Jellyfin server 12.0 or newer.

## Verification boundary

The code builds as an Android application. This workspace has no connected
Android device and the server media libraries observed while creating the app
were empty. Downloading and offline playback still need a real-device test with
an actual media item, including restarting the app with the network disabled.

The app's visual design is inspired by the streaming layout requested for
Piterflix. A literal pixel-for-pixel copy of Netflix on every screen is not
claimed or verified.
