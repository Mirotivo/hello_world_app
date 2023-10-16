# Getting Started with Flutter on Windows:

## 1. Install JDK

Download and install JDK 17 from the official Oracle website:
[Download JDK 17 for Windows](https://www.oracle.com/java/technologies/downloads/#jdk17-windows)

Set the following environment variables:
- `JAVA_HOME`: `C:\Program Files\Java\jdk-17`

Add the following paths to your system's `PATH`:
- `%JAVA_HOME%\bin`

## 2. Get Android Command Line Tools

Download Android command line tools from the official Android Developers website:
[Download Android Command Line Tools](https://developer.android.com/studio)

Move the `cmdline-tools` folder to `C:\Program Files\Android\sdk`

Set the following environment variables:
- `ANDROID_HOME`: `C:\Program Files\Android\sdk`

Add the following paths to your system's `PATH`:
- `%ANDROID_HOME%\cmdline-tools\bin`

## 3. Download Required SDK Components

Use `sdkmanager` to download SDK components:

```bash
sdkmanager "platforms;android-29" --sdk_root="C:\Program Files\Android\sdk"
sdkmanager "system-images;android-29;default;x86_64" --sdk_root="C:\Program Files\Android\sdk"
sdkmanager "build-tools;29.0.3" --sdk_root="C:\Program Files\Android\sdk"
sdkmanager "platform-tools" --sdk_root="C:\Program Files\Android\sdk"
sdkmanager "cmdline-tools;latest" --sdk_root="C:\Program Files\Android\sdk"
sdkmanager "emulator" --sdk_root="C:\Program Files\Android\sdk"

sdkmanager --licenses --sdk_root="C:\Program Files\Android\sdk"
```

## 3. Download Flutter

Get the Flutter SDK for Windows from the official Flutter website:
[Download Flutter for Windows](https://docs.flutter.dev/get-started/install/windows)

Move the `flutter` folder to `C:\Program Files\Android`

Add the following paths to your system's `PATH`:
- `%ANDROID_HOME%\..\flutter\bin`

# Flutter App "hello_world_app"
```bash
flutter config --android-sdk "C:\Program Files\Android\sdk"
flutter doctor
flutter create hello_world_app
cd hello_world_app
flutter run
flutter build apk
```

# Release
```bash
keytool -genkeypair -v -keystore hello.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias hello-world
- Enter keystore password: 123456
  
flutter build apk --release
```