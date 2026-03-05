# AGENTS.md

## Cursor Cloud specific instructions

### Repository Status

This is an empty Android/Gradle project scaffold (`email-notify`). As of the initial setup, the repository contains only:

- `README.md` — project title
- `.gitignore` — configured for Android/Gradle/IntelliJ/Firebase

There is **no source code, no build configuration, and no dependencies** to install or run.

### Environment

- **Java**: OpenJDK 21 is available in the Cloud VM.
- **Gradle**: Not pre-installed. Once `build.gradle` / `settings.gradle` files are added, use the Gradle wrapper (`./gradlew`) which is standard for Android projects.
- **Android SDK**: Not available in the Cloud VM. Android projects typically require the Android SDK for compilation and emulator-based testing. Cloud VM is not well-suited for Android emulator testing (no GPU/KVM). Unit tests (`./gradlew test`) and lint (`./gradlew lint`) should work once the project is scaffolded.

### Development Notes

- When the project is scaffolded, use `./gradlew` (Gradle wrapper) rather than a global Gradle installation.
- Android instrumented tests (`./gradlew connectedAndroidTest`) will not work in Cloud VM without an emulator or device. Focus on local unit tests (`./gradlew test`).
- The `.gitignore` suggests Firebase may be used (`google-services.json` is ignored). If Firebase is integrated, a `google-services.json` file will need to be provided as a secret or configuration step.
