# LIFE OS — Android project

LIFE OS is a mobile-first, OLED-black personal organizer. It stores data locally on the device/browser using `localStorage`; it has no account, analytics, or cloud backend.

## Features included
- Daily dashboard with habit completion, water, workout sets, and focus totals
- Gym, home workout, cardio and mobility set logging (exercise, reps, weight, set, rest)
- Habits and routine presets, daily check-offs, progress percentage
- Water intake quick-add buttons and editable goal
- Focus timer presets (25, 50, and 5 minutes), completed-session log, distraction check-in
- Tasks with categories, priority, due dates, completion state
- Time blocks and daily review
- 7-day water and habit charts
- JSON export/import backup
- OLED-black styling, responsive layout, offline web app shell

## Fastest way to use on Android
1. Put the `web/` folder contents on a static HTTPS host, or run the project locally during development.
2. Open the site in Chrome on Android.
3. Use Chrome menu → **Install app** or **Add to Home screen**.
4. Open it from the new icon. Once loaded, the shell works offline. Data stays in that browser's app storage.

## Build a native APK (Android Studio)
This archive includes a simple native Android WebView wrapper and its assets under `android-wrapper/`. It is a source project, not a compiled APK. To build:
1. Install Android Studio and its Android SDK.
2. Open `android-wrapper/` in Android Studio.
3. Allow Gradle to sync and install any requested SDK components.
4. Select **Build → Build APK(s)**. Android Studio will show the APK location when finished.

The wrapper loads the app from packaged local assets, enables JavaScript and DOM storage, and does not need network access for the core features. Build with a current Android SDK and review the manifest/signing settings before distributing it.

## Run the web project
Requires Node.js 18+:
```bash
npm install
npm run start
```
To build the web files:
```bash
npm run build
```

## Data backup
Use Progress → Export backup. Keep the JSON file private. Importing a backup replaces current local data, so export a backup first if needed.


## Optional: build APK using GitHub Actions
The included `.github/workflows/build-apk.yml` workflow builds a debug APK on a GitHub push or manual workflow run. Push this project to a GitHub repository, then open **Actions → Build LIFE OS APK** and download the `LIFE-OS-debug-apk` artifact from the completed run. The APK is a debug build, suitable for personal testing, not Play Store release.
