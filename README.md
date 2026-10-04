# LiquidGalaxy_Aryaman

An early-stage Flutter controller app for a [Liquid Galaxy](https://github.com/LiquidGalaxyLAB) rig. The app connects to the rig's master machine over SSH.

## Current state

This is a prototype. The code currently has:

- **Splash screen**: plays a looping, muted intro video (`assets/splash_video.mp4`) with a "Liquid Galaxy" title for 4 seconds, then opens the main screen.
- **SSH connection check**: reads the saved master IP, port, username, password and number of rigs from `shared_preferences`. It then tries to open an SSH connection (using the `ssh2` package) and shows the result as a **Connected** / **Disconnected** status.
- **Control screen**: four placeholder buttons (`BUTTON 1`–`BUTTON 4`) that don't do anything yet.
- **Error dialog**: a GIF dialog (`giff_dialog`) that routes back to the main screen.
- Landscape-only orientation, GetX navigation, and a light/dark mode preference stored in `shared_preferences`.

Gaps you should know about:

- No screen lets you enter the connection settings yet, even though the code has text controllers for them.
- `assets/error.gif` is referenced in the code but not included in the repo.
- Some dependencies in `pubspec.yaml` (`google_maps_flutter`, `flutter_translate`, `http`, `url_launcher`, `permission_handler`, `path_provider`) are declared but not used yet.

## Stack

- Flutter / Dart (SDK `>=2.18.6 <3.0.0`)
- `ssh2`, `shared_preferences`, `get`, `video_player`, `giff_dialog`, `google_fonts`

## Running

```bash
flutter pub get
flutter run
```

If you add Google Maps features, replace `YOUR_GOOGLE_MAPS_API_KEY` in `android/app/src/main/AndroidManifest.xml` with your own key.

---

Originally published at [aryamans29002/LiquidGalaxy_Aryaman](https://github.com/aryamans29002/LiquidGalaxy_Aryaman).
