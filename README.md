# PlantLock 🌱 (Android APK)

**Plant trees with your camera to unlock social media.** Phone edition of PlantLock.

## Flow
1. **Start Planting** → camera opens (rear camera, screen kept awake)
2. Every second the app judges the live frame — **motion + greenery heuristic,
   fully on-device**: moving AND plant-green in frame = planting
3. **Not planting → the number does not move.** Planting → progress grows
   (10 planting-seconds = 1 tree)
4. **Minimum 2 trees** → 🌳 **UNLOCKED** — celebration, focus session over

## Honest limits
- Detection is an **on-device heuristic** (motion energy + green-pixel ratio) —
  no frames leave the phone, but it is not a trained "planting" classifier.
  The PC edition uses real CLIP zero-shot vision.
- Android apps can't edit the hosts file without root — phone version runs a
  **focus session** instead of system-wide blocking. The hosts-level social
  media lock lives in the PC edition (`PlantLock`).

## Build (already built: `android/app/build/outputs/apk/debug/app-debug.apk`)
```
npm install
npx cap sync android
cd android && gradlew assembleDebug
```
Requires JDK 17 + Android SDK (platform-34, build-tools 34.0.0).

## Install on phone
Copy `app-debug.apk` → phone → open → allow **Camera** when asked.
