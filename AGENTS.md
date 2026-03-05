# AGENTS.md

## Cursor Cloud specific instructions

### Repository Overview

`email-notify` 是一个 Android 项目（当前仓库处于初始化状态，尚无源代码）。`.gitignore` 配置为 Android/Gradle/IntelliJ/Firebase 项目。

### 已安装的开发环境

| 组件 | 版本 | 路径 |
|------|------|------|
| Java (OpenJDK) | 21 | 系统自带 |
| Android SDK | cmdline-tools 12.0 | `/opt/android-sdk` |
| Android Platform | API 34 | `/opt/android-sdk/platforms/android-34` |
| Build Tools | 34.0.0 | `/opt/android-sdk/build-tools/34.0.0` |
| Platform Tools | 37.0.0 | `/opt/android-sdk/platform-tools` |
| Gradle | 8.7 | `/opt/gradle-8.7` (系统级) |

### 环境变量

已在 `~/.bashrc` 中配置：
```
export ANDROID_HOME=/opt/android-sdk
export PATH=$PATH:$ANDROID_HOME/cmdline-tools/latest/bin:$ANDROID_HOME/platform-tools
```

### 常用命令

当项目有代码后，标准 Android Gradle 命令：
- 构建 Debug APK：`./gradlew assembleDebug`
- 运行单元测试：`./gradlew test`
- 运行 Lint 检查：`./gradlew lint`
- 清理构建：`./gradlew clean`

### 注意事项

- 使用 `./gradlew`（Gradle Wrapper）而非全局 `gradle` 命令
- Cloud VM 无 Android 模拟器（无 KVM/GPU），不支持 `connectedAndroidTest`，只能跑本地单元测试 (`./gradlew test`)
- `.gitignore` 包含 `google-services.json`，如使用 Firebase 需要通过 Secrets 提供该文件
- Java 21 与 AGP 8.3.x 兼容，如需升级 AGP 请确认 Java 兼容性
