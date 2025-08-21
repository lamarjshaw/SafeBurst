Lamar Shaw

SafeBurst README

Project Overview

SafeBurst is a personal-safety Android application designed for discreet emergency activation. With features like fake calls, GPS live location SMS, and silent notification muting, it helps users quietly escape or diffuse uncomfortable situations through a custom trigger phrase or shake gesture.

Directory Structure

SafeBurst/ ├── app/ 
├── src/main/java/com/safeburst/app/   # Java source code │   
├── res/layout/                        # XML layout files │   
├── res/drawable/                      # Icons/images │   
└── AndroidManifest.xml                # App manifest 
├── build.gradle                           # App-level Gradle config 
├── settings.gradle                        # Project-level Gradle config 
├── app-release.aab                        # Bundle for Play Store 
├── app-release.apk                        # Debug/release APK 
├── output-metadata.json                   # Build metadata 
├── README.md                              # This documentation 
└── LICENSE                                # License file

Java Source Code

Located at: app/src/main/java/com/safeburst/app/ 
Contains the core logic such as:
- MainActivity.java: Entry screen with Panic button and settings access
- FakeCallActivity.java: Simulated incoming call behavior
- SettingsActivity.java: Interface for customizing secret phrases and toggles

XML Layout Files

Located at: app/src/main/res/layout/ 
- activity_main.xml: Main screen UI with panic and settings toggles
- activity_fake_call.xml: UI for the fake call screen
- activity_settings.xml: UI for configuring preferences

Icons and Drawables

Located at: app/src/main/res/drawable/ 
Includes: 
- App icon
- Button images for Answer/Decline
- Background visuals

Android Manifest

Located at: app/src/main/AndroidManifest.xml 
Declares permissions: 
- android.permission.CALL_PHONE
- android.permission.SEND_SMS
- android.permission.ACCESS_FINE_LOCATION
Registers activities:
- MainActivity
- FakeCallActivity
- SettingsActivity

Build Files

- build.gradle: Contains dependencies like SpeechRecognizer, Location Services, MediaPlayer.
- settings.gradle: Declares the root project name and includes module app.

Build Artifacts

- app-release.apk: Signed installable app file
- app-release.aab: Android App Bundle for Play Store upload
- output-metadata.json: Contains metadata from the last build process
  
Installation Instructions

1. Clone this repo to your local machine.
2. Open in Android Studio.
3. Build > Build Bundle(s)/APK(s) > Build APK(s)
4. Install on your device for testing or push to Play Store using the .aab file.
   
Usage

- Launch SafeBurst and configure your secret phrase and actions in Settings.
- Activate the app using voice or shake gesture.
- Panic mode triggers the configured response (fake call, GPS text, mute notifications).

License

This project is licensed under the MIT License. SafeBurst was developed using Android Studio and is currently available on the Google Play Store. For full terms and usage permissions, please refer to the LICENSE file included in this repository.

Roadmap
- Integrate local database for logging incidents 
- Add support for dark mode and theming
- Explore iOS version using Swift

