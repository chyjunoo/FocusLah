# FocusLah
FocusLah is a productivity application designed to help users manage their time effectively and stay inspired throughout the workday. By combining execution tools with motivational resources, it serves as a complete mental workspace.
A beautiful and modern Android productivity application that combines task management, Pomodoro timer, and daily motivational quotes to help you stay focused and motivated.


## Features

### 📋 Task Management
- Create, complete, and delete tasks
- Set task priorities (High, Medium, Low)
- Visual priority indicators
- Clean and intuitive interface

### ⏰ Pomodoro Timer
- Focus sessions (25 minutes)
- Short breaks (5 minutes)
- Long breaks (15 minutes)
- Automatic session tracking
- Beautiful circular timer visualization
- Session counter

### 💡 Motivational Quotes (with RSS Feed Support!)
- **NEW: Fresh quotes from RSS feeds**
- Automatic fetching from BrainyQuote and other sources
- Daily motivational quotes
- Random quote generator
- 30+ local quotes (offline fallback)
- Share quotes with friends
- Beautiful card-based UI with RSS indicators

### 📰 Productivity Articles (NEW!)
- **Brand new Articles tab**
- Fetch articles from Zen Habits, Lifehack, and Pick the Brain
- Browse latest productivity tips and self-improvement content
- Tap to read full articles in browser
- Refresh to get latest content

### ⚙️ Settings
- App information
- Privacy policy
- Share app functionality
- Clean settings interface

## Technology Stack

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture**: MVVM (Model-View-ViewModel)
- **Networking**: Retrofit + OkHttp (for RSS feeds)
- **XML Parsing**: SimpleXML Converter
- **Minimum SDK**: 24 (Android 7.0)
- **Target SDK**: 34 (Android 14)
- **Material Design**: Material Design 3

## Key Libraries

- Jetpack Compose - Modern UI toolkit
- Compose Navigation - Navigation between screens
- ViewModel - Lifecycle-aware state management
- Kotlin Coroutines & Flow - Asynchronous programming
- Retrofit + OkHttp - RSS feed fetching and networking
- SimpleXML - RSS/XML parsing
- Material Design 3 - Beautiful, modern UI components

## Project Structure

```
app/
├── src/main/
│   ├── java/com/motivate/productivity/
│   │   ├── data/              # Data models
│   │   │   ├── Task.kt
│   │   │   ├── Quote.kt
│   │   │   └── TimerState.kt
│   │   ├── viewmodel/         # ViewModels
│   │   │   ├── TaskViewModel.kt
│   │   │   ├── TimerViewModel.kt
│   │   │   └── QuoteViewModel.kt
│   │   ├── ui/
│   │   │   ├── screens/       # Compose screens
│   │   │   │   ├── TasksScreen.kt
│   │   │   │   ├── TimerScreen.kt
│   │   │   │   ├── QuotesScreen.kt
│   │   │   │   └── SettingsScreen.kt
│   │   │   └── theme/         # Theme & styling
│   │   ├── navigation/        # Navigation
│   │   └── MainActivity.kt    # Entry point
│   └── res/                   # Resources
└── build.gradle.kts           # Build configuration
```

## Getting Started

### Prerequisites

- Android Studio Hedgehog (2023.1.1) or newer
- JDK 8 or higher
- Android SDK with API level 34

### Installation

1. Clone this repository:
```bash
git clone <your-repository-url>
cd "app dev 1"
```

2. Open the project in Android Studio

3. Sync Gradle files (should happen automatically)

4. Run the app on an emulator or physical device

### Building the APK

#### Debug Build
```bash
./gradlew assembleDebug
```
Output: `app/build/outputs/apk/debug/app-debug.apk`

#### Release Build
```bash
./gradlew assembleRelease
```
Output: `app/build/outputs/apk/release/app-release.apk`

## Play Store Compliance

This app is designed to be fully compliant with Google Play Store policies:

### Privacy
- ✅ Core data stored locally on device (tasks, timer history)
- ✅ No personal information collected or transmitted
- ✅ No third-party analytics or tracking
- ✅ RSS feeds fetched over secure HTTPS
- ✅ Privacy policy included and updated
- ✅ Transparent permission usage

### Permissions
- `INTERNET` - For fetching RSS feeds (quotes and articles)
- `ACCESS_NETWORK_STATE` - To check connectivity before fetching
- `POST_NOTIFICATIONS` - For timer completion notifications (optional)

### Offline Mode
- ✅ Works completely offline for core features
- ✅ Tasks and timer work without internet
- ✅ 30+ local quotes available offline
- ✅ RSS feeds only need internet for fresh content

### Content Rating
- Suitable for all ages
- No inappropriate content
- Educational and productivity-focused

### Security
- ✅ ProGuard enabled for release builds
- ✅ No sensitive data transmission
- ✅ Secure local data storage

## Publishing to Play Store

### Before Publishing

1. **Update Privacy Policy URL**
   - Edit `PRIVACY_POLICY.md` with your contact information
   - Host privacy policy on a publicly accessible website
   - Update URL in `app/src/main/java/com/motivate/productivity/ui/screens/SettingsScreen.kt`

2. **Create App Icon**
   - Create launcher icons in appropriate sizes
   - Place in `app/src/main/res/mipmap-*` folders
   - Use Android Studio's Image Asset tool

3. **Generate Signing Key**
```bash
keytool -genkey -v -keystore my-release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias my-key-alias
```

4. **Configure Signing in build.gradle.kts**
```kotlin
android {
    signingConfigs {
        create("release") {
            storeFile = file("my-release-key.jks")
            storePassword = "your-store-password"
            keyAlias = "my-key-alias"
            keyPassword = "your-key-password"
        }
    }
    buildTypes {
        release {
            signingConfig = signingConfigs.getByName("release")
            // ...
        }
    }
}
```

5. **Build Release APK/AAB**
```bash
./gradlew bundleRelease
```

### Play Store Listing

1. **App Description**: Focus on productivity, motivation, and simplicity
2. **Screenshots**: Take screenshots of all 4 main screens
3. **Feature Graphic**: Create 1024x500px banner
4. **Category**: Productivity
5. **Content Rating**: Complete questionnaire (should be rated for Everyone)
6. **Target Audience**: All ages

## Recent Updates

### Version 1.0.1 (Latest)
- ✨ **NEW**: RSS feed integration for quotes
- ✨ **NEW**: Productivity Articles tab
- 🌐 Fetch fresh motivational content from the web
- 📱 Smart offline mode with local fallback
- 🎨 RSS status indicators in UI
- 🔒 Privacy-focused implementation

## Future Enhancements

Potential features for future versions:
- User-configurable RSS feeds in settings
- Task categories/tags
- Task due dates and reminders
- Custom timer durations
- Save favorite articles
- Offline article caching
- Statistics and analytics
- Dark/light theme toggle
- Data export/import
- Widget support
- Notification customization

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, questions, or feedback, please contact:
- Email: [Your email]
- GitHub Issues: [Your repository URL]

## Acknowledgments

- Motivational quotes compiled from various public domain sources
- Icons from Material Design Icons
- UI inspired by Material Design 3 guidelines

---

**Made with ❤️ using Jetpack Compose**
