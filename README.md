# Face Dot Art — Android App

WebView-based Android app: camera permission Android se properly leta hai,
phir wahi face-dot-art effect (MediaPipe FaceMesh + RGB dots) ek fullscreen
WebView ke andar chalata hai.

## Setup (Android Studio)

1. Android Studio khol ke **File → Open** → is `FaceDotArt` folder ko select karo.
2. Gradle sync hone do (pehli baar thoda time lega — internet chahiye).
   - Agar "Gradle wrapper missing" ka prompt aaye, "OK / Use Gradle Wrapper" pe click kar dena — Android Studio khud download kar lega.
3. Phone ko USB se connect karo (USB debugging ON) ya emulator use karo.
4. Green **Run ▶** button dabao.

## Kya expect karna hai

- App khulte hi camera permission popup aayega — **Allow** karna.
- Front camera on hoke face detect karega, RGB dots se face draw hoga
  (cyan = contour, magenta = eyes/brows, yellow = lips).
- Internet zaroori hai kyunki face-detection library (MediaPipe) CDN se load hoti hai.

## Files

- `app/src/main/java/.../MainActivity.kt` — camera permission + WebView setup
- `app/src/main/assets/face-dot-art.html` — face detection aur dot-drawing logic
- `app/src/main/AndroidManifest.xml` — CAMERA aur INTERNET permissions

## Real APK banane ke liye

Android Studio mein: **Build → Build Bundle(s) / APK(s) → Build APK(s)**
Output milega: `app/build/outputs/apk/debug/app-debug.apk` — ye file
seedha kisi bhi Android phone pe install ho sakti hai.

## Agla step (offline / better performance)

Abhi ye WebView + CDN-based demo hai (internet chahiye, thoda slow).
Agar chaho to isko **native** bana sakte hain — Kotlin + CameraX +
on-device MediaPipe Face Landmarker SDK use karke, jo offline chalega
aur zyada smooth/fast hoga. Bata dena agar wo version banana hai.
