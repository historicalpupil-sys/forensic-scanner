# Building the Universal Portable Forensic 3D Scanner Android APK

Because cloud AI sandboxes do not include the multi-gigabyte Android NDK/SDK (`android.jar`, `aapt2`, `d8`, and Gradle Maven repositories) or outbound internet access, this archive contains the **complete, ready-to-compile Flutter + Android CameraX source tree** and a **1-click GitHub Actions Cloud APK Builder**.

## Option A: Build the APK in the Cloud (Zero Local Setup via GitHub Actions)

1. Create a new repository on [GitHub](https://github.com/new) and upload/push the contents of this folder.
2. Open the **Actions** tab in your GitHub repository and select **Build Forensic 3D Scanner Android APK**.
3. Click **Run workflow**. Within ~3 minutes, GitHub's Ubuntu runner installs JDK 17, Android SDK 34, and Flutter 3.24, compiles both `app-debug.apk` and `app-release.apk`, and attaches `UniversalForensicScanner-Android-APKs.zip` to the workflow run for direct download to your phone.

## Option B: Build the APK Locally (Flutter CLI / Android Studio)

1. Install [Flutter SDK](https://docs.flutter.dev/get-started/install) and Android Studio (with Android SDK Platform 34).
2. Open a terminal in this unzipped folder and run:
   ```bash
   flutter create . --project-name universal_forensic_scanner --org com.forensicscanner --platforms android
   flutter pub get
   flutter build apk --release
   ```
3. Install the compiled APK (`build/app/outputs/flutter-apk/app-release.apk`) onto your Android phone via USB debugging:
   ```bash
   adb install build/app/outputs/flutter-apk/app-release.apk
   ```
