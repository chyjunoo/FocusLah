# FocusLah

Effective Date: January 11, 2026

A beautiful and modern Android productivity application that combines task management, adjustable Pomodoro timer, motivational quotes from APIs, and curated productivity articles to help you stay focused and motivated.

**Latest Version:** 1.0.0  
**Target SDK:** 35 (Android 15)  
**Minimum SDK:** 24 (Android 7.0+)

## Features

### 📋 Task Management
- Create, complete, and delete tasks
- Set task priorities (HIGH, MID, LOW)
- Visual priority badges with color coding
- Smart sorting (incomplete first, then by priority)
- Modern card-based UI with Material Design 3
- Clean and intuitive interface

### ⏰ Adjustable Pomodoro Timer
- **Fully customizable timer duration**
- +/- buttons to adjust time in 1-minute increments
- Keyboard input for precise time entry
- Focus and Break modes
- Automatic session tracking
- Beautiful circular timer with gradient progress
- Timer completion notifications with vibration
- Session counter with stats card
- "Start Leh" and "Stop Pls" buttons (with personality!)

### 💡 Motivational Quotes (API-Powered!)
- **Primary: Quotable.io API** (100,000+ verified quotes)
- Automatic fetching from famous people only
- No "Unknown" authors - all quotes from verified sources
- RSS feed fallback for additional variety
- 50+ curated local quotes (offline fallback)
- Random quote generator
- Share quotes with friends
- Beautiful card-based UI with online/offline indicators
- HTML entity decoding for perfect text display

### 📰 Productivity Articles
- **Curated from 10+ premium productivity blogs**
- Sources: James Clear, Cal Newport, Zen Habits, Lifehack, and more
- English-only content with quality filtering
- Author diversity (max 3 articles per author)
- HTML entity decoding for clean text
- Tap to read full articles in browser
- Refresh to get latest content
- Modern card-based layout

### ⚙️ Settings
- In-app Privacy Policy dialog (scrollable, comprehensive)
- About dialog with app information
- Share app functionality
- Modern blue & white Material Design 3 theme
- Clean, organized settings interface

## Technology Stack

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Architecture**: MVVM (Model-View-ViewModel)
- **Networking**: Retrofit + OkHttp
- **APIs**: Quotable.io for quotes
- **XML Parsing**: SimpleXML Converter (RSS feeds)
- **JSON Parsing**: Gson (API responses)
- **Minimum SDK**: 24 (Android 7.0+)
- **Target SDK**: 35 (Android 15)
- **Material Design**: Material Design 3
- **Build Tools**: Gradle 8.5+, ProGuard/R8

## Key Libraries

- **Jetpack Compose** - Modern declarative UI toolkit
- **Compose Navigation** - Type-safe navigation between screens
- **ViewModel & LiveData** - Lifecycle-aware state management
- **Kotlin Coroutines & Flow** - Asynchronous programming
- **Retrofit 2.9.0** - Type-safe HTTP client
- **OkHttp 4.12.0** - HTTP client with logging interceptor
- **SimpleXML** - RSS/XML feed parsing
- **Gson 2.10.1** - JSON parsing for API responses
- **Material Design 3** - Beautiful, modern UI components
- **Android Notifications** - Timer completion alerts with vibration

## Project Structure

```
app/
├── src/main/
│   ├── java/com/motivate/productivity/
│   │   ├── api/                    # API integrations
│   │   │   ├── ApiConfig.kt
│   │   │   ├── ApiResponse.kt
│   │   │   ├── BaseApiService.kt
│   │   │   └── QuotesApi.kt
│   │   ├── data/                   # Data models
│   │   │   ├── Task.kt
│   │   │   ├── Quote.kt
│   │   │   ├── Article.kt
│   │   │   ├── RssFeed.kt
│   │   │   └── TimerState.kt
│   │   ├── viewmodel/              # ViewModels
│   │   │   ├── TaskViewModel.kt
│   │   │   ├── TimerViewModel.kt
│   │   │   ├── QuoteViewModel.kt
│   │   │   └── ArticlesViewModel.kt
│   │   ├── repository/             # Data repositories
│   │   │   └── RssFeedRepository.kt
│   │   ├── network/                # Network configuration
│   │   │   ├── RetrofitClient.kt
│   │   │   └── RssService.kt
│   │   ├── notification/           # Notifications
│   │   │   └── TimerNotificationHelper.kt
│   │   ├── ui/
│   │   │   ├── screens/            # Compose screens
│   │   │   │   ├── SplashScreen.kt
│   │   │   │   ├── TasksScreen.kt
│   │   │   │   ├── TimerScreen.kt
│   │   │   │   ├── QuotesScreen.kt
│   │   │   │   ├── ArticlesScreen.kt
│   │   │   │   └── SettingsScreen.kt
│   │   │   └── theme/              # Theme & styling
│   │   │       ├── Theme.kt
│   │   │       ├── Color.kt
│   │   │       └── Shape.kt
│   │   ├── navigation/             # Navigation
│   │   │   └── Screen.kt
│   │   └── MainActivity.kt         # Entry point
│   ├── res/                        # Resources
│   │   ├── values/
│   │   │   ├── strings.xml
│   │   │   ├── colors.xml
│   │   │   └── themes.xml
│   │   └── mipmap-*/               # App icons
│   └── AndroidManifest.xml
├── build.gradle.kts                # Build configuration
└── proguard-rules.pro              # ProGuard rules for release
```

## Getting Started

### Prerequisites

- Android Studio Hedgehog (2023.1.1) or newer
- JDK 8 or higher
- Android SDK with API level 35 (Android 15)
- Gradle 8.5 or higher

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
- `INTERNET` - For fetching quotes from APIs and RSS feeds
- `ACCESS_NETWORK_STATE` - To check connectivity before fetching
- `POST_NOTIFICATIONS` - For timer completion notifications (optional)
- `VIBRATE` - For haptic feedback when timer completes

### Offline Mode
- ✅ Works completely offline for core features
- ✅ Tasks and timer work without internet
- ✅ 50+ local quotes available offline (famous people only)
- ✅ APIs and RSS feeds only need internet for fresh content
- ✅ Graceful degradation when offline

### Content Rating
- Suitable for all ages
- No inappropriate content
- Educational and productivity-focused

### Security
- ✅ ProGuard/R8 enabled for release builds with comprehensive rules
- ✅ No sensitive data transmission
- ✅ Secure local data storage
- ✅ HTTPS for all network requests
- ✅ Cleartext traffic support for HTTP RSS feeds

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

### Version 1.0.0 (Latest - January 2026)
- ✨ **NEW**: Quotable.io API integration for quotes (100,000+ quotes)
- ✨ **NEW**: Productivity Articles tab with 10+ curated sources
- ✨ **NEW**: Adjustable Pomodoro timer (customizable duration)
- ✨ **NEW**: Timer notifications with vibration
- ✨ **NEW**: Animated splash screen
- ✨ **NEW**: In-app Privacy Policy dialog
- 🎨 **UI Redesign**: Modern blue & white Material Design 3 theme
- 🎨 Card-based layouts throughout
- 🔧 HTML entity decoding for perfect text display
- 🔧 English-only article filtering
- 🔧 Author diversity in articles (max 3 per author)
- 🔧 Famous people quotes only (no "Unknown" authors)
- 🔧 Smart priority sorting for tasks (HIGH > MID > LOW)
- 🔧 ProGuard rules for release builds
- 🌐 API 35 (Android 15) support
- 📱 Smart offline mode with multi-layer fallback
- 🔒 Privacy-focused implementation (no tracking, no analytics)

## Future Enhancements

Potential features for future versions:
- ✅ ~~Custom timer durations~~ (Implemented!)
- ✅ ~~Timer notifications~~ (Implemented!)
- ✅ ~~API integration for quotes~~ (Implemented!)
- User-configurable RSS feeds in settings
- Task categories/tags
- Task due dates and reminders
- Save favorite articles
- Offline article caching
- Statistics and productivity analytics
- Dark/light theme toggle
- Data export/import
- Widget support
- Notification sound customization
- Cloud backup (optional)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, questions, or feedback, please contact:
- Email: focuslah.team@gmail.com
- GitHub Issues: [Your repository URL]

## Acknowledgments

- **Quotable.io** - Free quotes API with 100,000+ verified quotes
- **RSS Feed Sources**: James Clear, Cal Newport, Zen Habits, Lifehack, and more
- Motivational quotes from famous historical figures and thought leaders
- Icons from Material Design Icons
- UI inspired by Material Design 3 guidelines
- Built with Jetpack Compose and modern Android development practices

## Key Features Highlights

### 🎨 Modern UI/UX
- Beautiful blue & white color scheme
- Card-based layouts with elevation
- Circular progress indicators
- Gradient backgrounds
- Smooth animations
- Material Design 3 components

### 🔒 Privacy-First
- No user tracking
- No analytics
- No ads
- All data stored locally
- Transparent data handling
- Open source

### ⚡ Performance
- ProGuard optimized release builds
- Efficient network requests
- Smart caching
- Minimal battery usage
- Fast startup time
- Responsive UI

### 🌐 Network Features
- Quotable.io API integration
- RSS feed parsing
- HTML entity decoding
- Graceful error handling
- Offline fallback
- Auto-retry on failure

---

**Made with ❤️ using Jetpack Compose**

**FocusLah** - Stay focused, stay motivated! 🚀
