---
name: mobile-translation-dictionary
delivery: reference
description: |
  Словарь терминологии мобильной разработки (iOS, Android, кросс-платформенной)
  для перевода технических статей и унификации терминов в русскоязычных
  материалах VK Tech. Покрывает Swift/SwiftUI/UIKit, Kotlin/Jetpack
  Compose/Android SDK, React Native, Flutter, Kotlin Multiplatform, App Store /
  Google Play, push-уведомления, биометрию, MDM, мобильную безопасность.
  Активируется автоматически по триггерам темы; пригоден любому автору и
  редактору мобильного контента, не только модулю перевода. Источники:
  документация Apple/Google, переводы Хабра (Сбер/VK/Avito/Yandex Mobile),
  MOBIUS-конференции, методология «Альянса ПРО».
activation:
  - "mobile"
  - "мобильный"
  - "мобильная разработка"
  - "mobile development"
  - "ios"
  - "android"
  - "swift"
  - "swiftui"
  - "uikit"
  - "objective-c"
  - "objc"
  - "kotlin"
  - "котлин"
  - "java (android)"
  - "jetpack compose"
  - "compose"
  - "android sdk"
  - "xcode"
  - "android studio"
  - "app store"
  - "google play"
  - "play market"
  - "play console"
  - "appstore connect"
  - "testflight"
  - "react native"
  - "flutter"
  - "dart"
  - "kotlin multiplatform"
  - "kmp"
  - "kmm"
  - "expo"
  - "xamarin"
  - "ionic"
  - "cordova"
  - "capacitor"
  - "nativescript"
  - "activity"
  - "fragment"
  - "viewcontroller"
  - "view controller"
  - "intent"
  - "broadcast receiver"
  - "content provider"
  - "service (android)"
  - "push notifications"
  - "пуш-уведомления"
  - "apns"
  - "fcm"
  - "deeplink"
  - "deep link"
  - "universal links"
  - "app links"
  - "in-app purchase"
  - "iap"
  - "subscriptions"
  - "biometric"
  - "face id"
  - "touch id"
  - "keychain"
  - "keystore"
  - "mdm"
  - "mobile device management"
  - "rusbitech mdm"
  - "rumobile"
  - "rustore"
  - "rumarket"
  - "huawei appgallery"
---

# Mobile Translation Dictionary

Словарь терминологии мобильной разработки (iOS, Android, кросс-платформенные фреймворки). Используется для перевода статей и для унификации терминологии в любых русскоязычных материалах VK Tech.

**Для переводчиков:** все 19 разделов применимы, включая падежные формы и типовые ошибки.
**Для авторов SEO-статей, документации, пресс-релизов:** опирайся в первую очередь на разделы 2-15 (терминологические таблицы по платформам, фреймворкам, инструментам). Разделы 17-19 (падежные формы, типовые ошибки переводчика) специфичны для перевода.

## Принципы

1. **Имена ОС и платформ — оригинал.** iOS, iPadOS, macOS, watchOS, tvOS, visionOS, Android, HarmonyOS, Wear OS. Не «иОС».
2. **Имена языков программирования — оригинал.** Swift, Objective-C, Kotlin, Java, Dart, C++. Допустимо «свифт», «котлин» в разговорной речи.
3. **Имена фреймворков и SDK — оригинал.** SwiftUI, UIKit, Jetpack Compose, React Native, Flutter, Kotlin Multiplatform.
4. **Названия системных компонентов — оригинал, при первом упоминании поясняй.** Activity, Fragment, ViewController, Intent, Service, BroadcastReceiver, ContentProvider.
5. **Имена API — оригинал.** CoreData, RealityKit, ARKit, MLKit, CameraX, WorkManager, Room.
6. **Аббревиатуры — оригинал.** SDK, NDK, IDE, APK, AAB, IPA, DSYM, PCH, ARM64, iOS, OEM, OTA, MDM, BYOD, APNs, FCM, IAP, ASO.
7. **Российская специфика — точные русские названия.** RuStore, RuMarket, RuMobile, Rusbitech MDM. См. также `security-translation-dictionary`.

## Раздел 1. Базовые понятия мобильной разработки

| English | Русский (рекомендуемый) | Альтернативы | Комментарий |
|---------|-------------------------|--------------|-------------|
| Mobile development | мобильная разработка | — | — |
| Mobile app / application | мобильное приложение / мобильное приложение | — | — |
| Native app | нативное приложение | — | — |
| Cross-platform app | кросс-платформенное приложение | — | — |
| Hybrid app | гибридное приложение | — | — |
| Web app | веб-приложение | — | — |
| PWA (Progressive Web App) | PWA | См. `frontend-translation-dictionary` |
| Mobile-first | mobile-first | Не переводится |
| OS (Operating System) | ОС / операционная система | — |
| SDK (Software Development Kit) | SDK | При первом упоминании — расшифровка |
| NDK (Native Development Kit) | NDK | Android |
| IDE (Integrated Development Environment) | IDE / среда разработки | — |
| API (Mobile API) | API | — |
| ABI (Application Binary Interface) | ABI | — |
| Build | сборка / build | — |
| Release / Debug build | release / debug сборка | — |
| Architecture (CPU) | архитектура | ARM64, x86_64 |
| Bytecode | байт-код | — |
| Compilation | компиляция | — |

## Раздел 2. iOS / Apple платформы

| English | Русский | Комментарий |
|---------|---------|-------------|
| iOS | iOS | Не переводится |
| iPadOS | iPadOS | — |
| macOS | macOS | — |
| watchOS | watchOS | — |
| tvOS | tvOS | — |
| visionOS | visionOS | Apple Vision Pro |
| Apple Watch | Apple Watch | — |
| Apple TV | Apple TV | — |
| Apple Vision Pro | Apple Vision Pro | — |
| iPhone, iPad, Mac | iPhone, iPad, Mac | Не переводить |
| Xcode | Xcode | — |
| Instruments | Instruments | Профилирование |
| Simulator | симулятор / Simulator | — |
| TestFlight | TestFlight | — |
| App Store | App Store | — |
| App Store Connect | App Store Connect | — |
| App Review | App Review / ревью приложений | — |
| Apple Developer | Apple Developer | — |
| Provisioning profile | provisioning-профиль | — |
| Certificate | сертификат | — |
| Bundle ID | bundle ID | — |
| Capabilities | capabilities / возможности | — |
| Entitlements | entitlements | — |
| Code signing | подпись кода / code signing | — |
| Notarization | нотаризация / notarization | macOS |
| App Thinning | App Thinning | — |
| Bitcode | Bitcode | Устар. |
| App Clip | App Clip | — |
| Widget | виджет | — |
| Extension (iOS) | extension / расширение | — |
| Sandbox (iOS) | sandbox / песочница | — |
| Keychain | Keychain | — |
| iCloud, CloudKit | iCloud, CloudKit | — |
| Sign in with Apple | Sign in with Apple | — |
| App Tracking Transparency (ATT) | ATT / App Tracking Transparency | — |
| IDFA (Identifier for Advertisers) | IDFA | — |

## Раздел 3. Swift / SwiftUI / UIKit

| English | Русский | Комментарий |
|---------|---------|-------------|
| Swift | Swift | Не переводится |
| Swift 6 | Swift 6 | — |
| Objective-C | Objective-C | — |
| Objective-C++ | Objective-C++ | — |
| SwiftUI | SwiftUI | — |
| UIKit | UIKit | — |
| AppKit | AppKit | macOS |
| Combine | Combine | Reactive framework |
| async / await (Swift) | async / await | — |
| Actor (Swift) | actor / актор | Swift Concurrency |
| Sendable | Sendable | — |
| Property wrapper | property wrapper | `@State`, `@Binding` |
| Result builder | result builder | — |
| ViewController | ViewController | UIKit |
| View | View | SwiftUI / UIKit |
| Modifier | модификатор / modifier | SwiftUI |
| State / Binding / Environment | State / Binding / Environment | SwiftUI |
| ObservableObject / @Observable | ObservableObject / `@Observable` | — |
| Storyboard | Storyboard | UIKit |
| Auto Layout | Auto Layout | — |
| Constraint | constraint / констрейнт / ограничение | — |
| Stack View | Stack View | — |
| Table View / Collection View | Table View / Collection View | — |
| Delegate / DataSource | delegate / dataSource | UIKit pattern |
| Protocol | протокол | Swift |
| Extension (Swift) | extension / расширение | — |
| Optional | Optional / опциональный тип | — |
| Closure | замыкание / closure | — |
| Trailing closure | trailing closure | — |
| `@MainActor` | `@MainActor` | — |
| Swift Package Manager (SPM) | SPM | — |
| CocoaPods | CocoaPods | — |
| Carthage | Carthage | — |

## Раздел 4. iOS-фреймворки

| English | Русский | Комментарий |
|---------|---------|-------------|
| Foundation | Foundation | — |
| Core Data | Core Data | — |
| SwiftData | SwiftData | — |
| Core Animation | Core Animation | — |
| Core Graphics | Core Graphics | — |
| Core Location | Core Location | — |
| MapKit | MapKit | — |
| AVFoundation | AVFoundation | Аудио / видео |
| AVKit | AVKit | — |
| ARKit | ARKit | AR |
| RealityKit | RealityKit | — |
| SceneKit | SceneKit | 3D |
| Metal | Metal | GPU |
| CoreML | CoreML | ML |
| Vision | Vision | CV |
| Speech | Speech | — |
| HealthKit | HealthKit | — |
| HomeKit | HomeKit | — |
| WidgetKit | WidgetKit | — |
| StoreKit | StoreKit | IAP |
| PushKit / UserNotifications | PushKit / UserNotifications | Push |
| WatchConnectivity | WatchConnectivity | — |
| BackgroundTasks | BackgroundTasks | — |
| WebKit, WKWebView | WebKit, WKWebView | — |

## Раздел 5. Android

| English | Русский | Комментарий |
|---------|---------|-------------|
| Android | Android | Не переводится |
| Android Studio | Android Studio | — |
| Gradle / Kotlin DSL | Gradle | Build system |
| AGP (Android Gradle Plugin) | AGP | — |
| ADB (Android Debug Bridge) | ADB | — |
| Logcat | Logcat | — |
| Emulator | эмулятор | — |
| AVD (Android Virtual Device) | AVD | — |
| Profiler | профилировщик / Profiler | — |
| Google Play | Google Play | — |
| Play Console | Play Console | — |
| Play Store | Play Store / Google Play Store | — |
| Play Services | Play Services / Google Play Services | — |
| GMS (Google Mobile Services) | GMS | — |
| AOSP (Android Open Source Project) | AOSP | — |
| Android Open Source | Android Open Source | — |
| Wear OS | Wear OS | — |
| Android Auto | Android Auto | — |
| Android TV | Android TV | — |
| ChromeOS | ChromeOS | — |
| HarmonyOS, AppGallery | HarmonyOS, AppGallery | Huawei |
| RuStore | RuStore | Российский магазин |
| RuMarket / NashStore | RuMarket / NashStore | — |
| APK (Android Package) | APK | — |
| AAB (Android App Bundle) | AAB | — |
| Manifest (AndroidManifest.xml) | манифест | — |
| Resources (res/) | ресурсы | strings.xml, drawable, layout |
| Drawable | drawable / графический ресурс | — |
| Vector drawable | vector drawable | — |
| 9-patch | 9-patch | — |
| Density buckets (mdpi, hdpi, xhdpi, xxhdpi, xxxhdpi) | mdpi/hdpi/xhdpi/xxhdpi/xxxhdpi | — |
| Permissions | разрешения | `<uses-permission>` |
| Runtime permissions | runtime-разрешения | Android 6+ |
| Scoped storage | scoped storage | Android 10+ |
| App Links | App Links | — |
| Deep Links | Deep Links / диплинки | — |
| Sandbox (Android) | sandbox / песочница | — |

## Раздел 6. Kotlin / Jetpack Compose / Android SDK

| English | Русский | Комментарий |
|---------|---------|-------------|
| Kotlin | Kotlin | Не переводится |
| Kotlin Multiplatform (KMP) | KMP / Kotlin Multiplatform | — |
| Kotlin Multiplatform Mobile (KMM) | KMM | — |
| Java (Android) | Java | — |
| Coroutines | корутины | Kotlin |
| Flow | Flow | Kotlin Flow |
| StateFlow / SharedFlow | StateFlow / SharedFlow | — |
| suspend function | suspend-функция | — |
| Channel | Channel | Coroutines |
| Sealed class | sealed-класс | Kotlin |
| Data class | data-класс | — |
| Extension function | extension-функция | — |
| Lambda | лямбда | — |
| Scope function (let, run, with, apply, also) | scope-функция | — |
| Jetpack Compose | Jetpack Compose | Не переводится |
| Composable | composable / композабл | — |
| `@Composable` | `@Composable` | — |
| State (Compose) | состояние / state | — |
| `remember` / `mutableStateOf` | `remember` / `mutableStateOf` | — |
| Recomposition | recomposition / перекомпозиция | — |
| Modifier | модификатор / Modifier | — |
| Slot (Compose) | slot | — |
| Material 3 | Material 3 / Material You | — |
| Compose Multiplatform | Compose Multiplatform | — |
| AndroidX | AndroidX | — |
| Jetpack | Jetpack | Набор библиотек |
| Lifecycle | жизненный цикл / Lifecycle | — |
| LiveData | LiveData | — |
| ViewModel | ViewModel | — |
| Room | Room | ORM |
| WorkManager | WorkManager | — |
| Navigation Component | Navigation Component | — |
| Hilt | Hilt | DI |
| Dagger | Dagger | — |
| Koin | Koin | DI |
| Activity | Activity | Не переводить — имя компонента |
| Fragment | Fragment | — |
| Intent | Intent | «Создать Intent», «обработать Intent» |
| Service (Android) | Service | Не путать с веб-Service |
| BroadcastReceiver | BroadcastReceiver | — |
| ContentProvider | ContentProvider | — |
| Bundle | Bundle | Не путать с фронтенд-bundle |
| Parcelable / Serializable | Parcelable / Serializable | — |
| RecyclerView | RecyclerView | — |
| ConstraintLayout | ConstraintLayout | — |
| ViewBinding / DataBinding | ViewBinding / DataBinding | — |
| Camera2 / CameraX | Camera2 / CameraX | — |
| ML Kit | ML Kit | Google |
| Firebase | Firebase | — |
| Firestore | Firestore | — |
| Crashlytics | Crashlytics | — |
| Analytics (Firebase) | Firebase Analytics | — |
| Remote Config | Remote Config | — |

## Раздел 7. Кросс-платформенные фреймворки

| English | Русский | Комментарий |
|---------|---------|-------------|
| React Native | React Native | Не переводится |
| Expo | Expo | — |
| Hermes | Hermes | RN JS engine |
| New Architecture (RN) | New Architecture | RN |
| Fabric / TurboModules | Fabric / TurboModules | RN internals |
| Bridge | bridge / мост | RN |
| Metro | Metro | RN bundler |
| Flipper | Flipper | Debug tool |
| Flutter | Flutter | Не переводится |
| Dart | Dart | — |
| Widget (Flutter) | Widget | Не путать с iOS Widget |
| StatelessWidget / StatefulWidget | StatelessWidget / StatefulWidget | — |
| BuildContext | BuildContext | — |
| Engine (Flutter) | Engine | — |
| Skia | Skia | Graphics engine |
| Impeller | Impeller | Новый рендерер Flutter |
| Hot reload / Hot restart | hot reload / hot restart | — |
| Pub.dev | pub.dev | Dart packages |
| Xamarin / .NET MAUI | Xamarin / .NET MAUI | — |
| Ionic / Capacitor / Cordova | Ionic / Capacitor / Cordova | Hybrid |
| NativeScript | NativeScript | — |
| Compose Multiplatform | Compose Multiplatform | — |

## Раздел 8. Push, deeplinks, IAP

| English | Русский | Комментарий |
|---------|---------|-------------|
| Push notification | push-уведомление | Через дефис |
| APNs (Apple Push Notification service) | APNs | iOS |
| FCM (Firebase Cloud Messaging) | FCM | Android |
| Hms Push | Hms Push | Huawei |
| Silent push | silent push / тихий push | — |
| Rich push | rich push | С изображениями |
| Notification permission | разрешение на уведомления | — |
| Provisional notifications | provisional notifications | iOS |
| Notification channel | канал уведомлений | Android 8+ |
| Notification category | категория уведомлений | iOS |
| Deep link | deep link / диплинк | — |
| Universal Links | Universal Links | iOS |
| App Links | App Links | Android |
| Custom URL scheme | custom URL scheme | — |
| Deferred deep link | deferred deep link | — |
| In-app purchase (IAP) | IAP / встроенная покупка | — |
| Subscriptions | подписки | — |
| Auto-renewable subscription | автоматически возобновляемая подписка | — |
| Consumable / Non-consumable | потребляемая / непотребляемая (покупка) | — |
| Restore purchases | восстановление покупок | — |
| Receipt validation | валидация чеков | — |
| StoreKit 2 | StoreKit 2 | iOS |
| Google Play Billing | Google Play Billing | Android |
| Promo codes | промокоды | — |

## Раздел 9. Безопасность мобильных приложений

| English | Русский | Комментарий |
|---------|---------|-------------|
| Mobile security | мобильная безопасность | См. также `security-translation-dictionary` |
| Biometric authentication | биометрическая аутентификация | — |
| Face ID | Face ID | iOS |
| Touch ID | Touch ID | iOS |
| Optic ID | Optic ID | visionOS |
| Fingerprint | отпечаток пальца | Android |
| BiometricPrompt | BiometricPrompt | Android |
| LocalAuthentication | LocalAuthentication | iOS |
| Keychain (iOS) | Keychain | — |
| Keystore (Android) | Keystore | — |
| EncryptedSharedPreferences | EncryptedSharedPreferences | — |
| App Transport Security (ATS) | App Transport Security / ATS | iOS |
| Network Security Config | Network Security Config | Android |
| Certificate pinning | certificate pinning | См. `security-translation-dictionary` |
| Root detection / Jailbreak detection | детект root / детект jailbreak | — |
| Tamper detection | tamper detection | — |
| Code obfuscation | обфускация кода | — |
| ProGuard / R8 | ProGuard / R8 | Android |
| Anti-debugging | anti-debugging | — |
| SafetyNet (deprecated) / Play Integrity | Play Integrity | Android |
| DeviceCheck / App Attest | DeviceCheck / App Attest | iOS |
| MDM (Mobile Device Management) | MDM / управление мобильными устройствами | — |
| EMM (Enterprise Mobility Management) | EMM | — |
| BYOD (Bring Your Own Device) | BYOD | — |
| COPE (Corporate-Owned, Personally Enabled) | COPE | — |
| **Rusbitech MDM, ALD Pro, RuMobile** | **Rusbitech MDM, ALD Pro, RuMobile** | Российские MDM |
| App Wrapping | app wrapping | — |
| Containerization | контейнеризация (мобильная) | — |

## Раздел 10. UI/UX-паттерны и компоненты

| English | Русский | Комментарий |
|---------|---------|-------------|
| Tab bar / Bottom navigation | Tab bar (iOS) / Bottom navigation (Android) | — |
| Navigation bar | навигационная панель | — |
| Toolbar | toolbar / тулбар | Android |
| Action bar | action bar | Устар. Android |
| Side menu / Drawer | side menu / drawer / боковое меню | — |
| Modal | модальное окно / modal | — |
| Sheet (bottom sheet, action sheet) | sheet / bottom sheet / action sheet | — |
| Alert / Toast / Snackbar | alert / toast / snackbar | — |
| Pull-to-refresh | pull-to-refresh / потяни для обновления | — |
| Swipe gesture | swipe / свайп | — |
| Tap / Long press | tap / long press | — |
| Pinch / Zoom | pinch / zoom | — |
| Drag and drop | drag and drop | — |
| Skeleton screen | skeleton screen / скелетон | — |
| Shimmer effect | shimmer / шиммер | — |
| Empty state | empty state / пустое состояние | — |
| Loading state | loading state | — |
| Onboarding | онбординг | — |
| Splash screen | splash screen / экран загрузки | — |
| Dark mode | тёмная тема / dark mode | — |
| Dynamic Type | Dynamic Type | iOS |
| Haptic feedback | тактильная отдача / haptic feedback | — |
| Voice over (iOS) / TalkBack (Android) | VoiceOver / TalkBack | — |

## Раздел 11. Магазины приложений и публикация

| English | Русский | Комментарий |
|---------|---------|-------------|
| App store (общее) | магазин приложений | — |
| App Store (Apple) | App Store | — |
| Google Play / Play Store | Google Play / Play Store | — |
| **RuStore** | **RuStore** | Российский магазин (VK) |
| **NashStore / RuMarket** | NashStore / RuMarket | Российские магазины |
| Huawei AppGallery | AppGallery | — |
| Samsung Galaxy Store | Galaxy Store | — |
| Amazon Appstore | Amazon Appstore | — |
| F-Droid | F-Droid | Open-source |
| App listing | страница приложения | — |
| App description | описание приложения | — |
| Screenshots | скриншоты | — |
| App icon | иконка приложения | — |
| App preview / Video preview | превью-видео | — |
| Keywords (ASO) | ключевые слова (ASO) | — |
| **ASO (App Store Optimization)** | ASO / оптимизация в магазинах приложений | — |
| Rating / Reviews | рейтинг / отзывы | — |
| Star rating | звёздный рейтинг | — |
| Featured app | featured app / рекомендуемое приложение | — |
| App review | ревью / модерация приложения | — |
| Rejection | reject / отклонение | — |
| App Store guidelines | App Store guidelines / правила App Store | — |
| Google Play policy | Google Play policy | — |
| In-app updates | in-app updates | Android |
| Phased release | phased release / поэтапный релиз | — |
| Internal testing | internal testing / внутреннее тестирование | — |
| Closed / Open testing | closed / open testing | Android |
| TestFlight (iOS) | TestFlight | — |
| Beta testers | бета-тестировщики | — |

## Раздел 12. Производительность и аналитика

| English | Русский | Комментарий |
|---------|---------|-------------|
| App performance | производительность приложения | — |
| App startup time / Launch time | время запуска | — |
| Cold start / Warm start / Hot start | cold/warm/hot start | — |
| ANR (Application Not Responding) | ANR | Android |
| FPS / Frame rate | FPS / частота кадров | — |
| Jank | джанк (подвисания UI) | — |
| Frame drop | frame drop / пропуск кадра | — |
| Memory leak | утечка памяти | — |
| Heap | heap / куча | — |
| GC (Garbage Collection) | GC / сборка мусора | — |
| Battery consumption | расход батареи | — |
| Wake lock | wake lock | Android |
| Background execution | фоновое выполнение | — |
| App size | размер приложения | — |
| Install size / Download size | размер установки / размер загрузки | — |
| App startup library | App Startup library | Android Jetpack |
| Baseline Profiles | Baseline Profiles | Android |
| R8 / Proguard shrinking | R8 / Proguard сжатие | — |
| Mobile analytics | мобильная аналитика | — |
| Firebase Analytics | Firebase Analytics | — |
| AppsFlyer | AppsFlyer | — |
| Adjust | Adjust | — |
| Amplitude | Amplitude | — |
| Mixpanel | Mixpanel | — |
| **AppMetrica (Яндекс)** | AppMetrica | Российская аналитика |
| **MyTracker (VK)** | MyTracker | Российская аналитика |
| Crash reporting | сбор отчётов о падениях | — |
| Crashlytics | Crashlytics | — |
| Sentry | Sentry | — |

## Раздел 13. CI/CD для мобильных приложений

| English | Русский | Комментарий |
|---------|---------|-------------|
| Mobile CI/CD | мобильный CI/CD | См. `devops-translation-dictionary` |
| Fastlane | Fastlane | Ruby tool |
| Bitrise | Bitrise | — |
| Codemagic | Codemagic | — |
| App Center | App Center | Microsoft |
| Xcode Cloud | Xcode Cloud | Apple CI |
| GitHub Actions (mobile) | GitHub Actions | — |
| GitLab CI (mobile) | GitLab CI | — |
| Match (Fastlane) | Match | Code signing |
| Gym (Fastlane) | Gym | iOS build |
| Pilot (Fastlane) | Pilot | TestFlight upload |
| Supply (Fastlane) | Supply | Play Store upload |
| App signing | подпись приложения | — |
| Upload key | upload key | Android |
| Code signing identity | code signing identity | iOS |
| Provisioning | provisioning | iOS |

## Раздел 14. Тестирование мобильных приложений

| English | Русский | Комментарий |
|---------|---------|-------------|
| Mobile testing | мобильное тестирование | — |
| Unit test (mobile) | unit-тест | — |
| Integration test | интеграционный тест | — |
| UI test | UI-тест | — |
| Espresso (Android) | Espresso | — |
| UI Automator | UI Automator | Android |
| XCUITest (iOS) | XCUITest | — |
| XCTest | XCTest | iOS unit testing |
| Quick / Nimble (Swift) | Quick / Nimble | — |
| Appium | Appium | Cross-platform |
| Detox (RN) | Detox | — |
| Maestro | Maestro | — |
| KIF (iOS) | KIF | — |
| Robolectric | Robolectric | Android |
| Mockito | Mockito | Android |
| MockK (Kotlin) | MockK | — |
| Cuckoo / Mockingbird (Swift) | Cuckoo / Mockingbird | — |
| Test pyramid | пирамида тестов | — |
| Device farm | device farm / парк устройств | — |
| Firebase Test Lab | Firebase Test Lab | — |
| AWS Device Farm | AWS Device Farm | — |
| BrowserStack App Live | BrowserStack App Live | — |
| Screenshot testing | screenshot-тестирование | — |

## Раздел 15. Специфика российского рынка

| English / контекст | Русский | Комментарий |
|--------------------|---------|-------------|
| Russian app store | **RuStore** (VK), **NashStore** (Госуслуги), **RuMarket** | Российские магазины приложений |
| Russian MDM | **Rusbitech MDM, ALD Pro Mobile, RuMobile, Astra Linux Mobile** | Сертифицированные ФСТЭК MDM |
| Russian mobile analytics | **AppMetrica (Яндекс), MyTracker (VK)** | — |
| Russian push delivery service | **RuStore Push (VK), AppMetrica Push (Яндекс)** | Альтернативы FCM/APNs |
| Russian map SDK | **2GIS SDK, Yandex MapKit, VK MapKit** | — |
| Russian biometric standards | **ЕБС (Единая биометрическая система)** | — |
| Russian app review | **Минцифры / ФСТЭК сертификация для госприложений** | — |
| Domestic OS for mobile | **Аврора ОС, RoseLinux Mobile** | Российские мобильные ОС |

## Раздел 16. Глаголы и действия

| English | Русский | Комментарий |
|---------|---------|-------------|
| to install | установить (приложение) | — |
| to uninstall | удалить (приложение) | — |
| to update (app) | обновить | — |
| to launch | запустить | — |
| to crash | упасть / крашнуться | «Приложение упало» |
| to deploy (mobile) | задеплоить / залить (в магазин) | — |
| to publish (app) | опубликовать (приложение) | — |
| to ship (release) | зарелизить / выкатить | — |
| to swipe | свайпнуть | — |
| to tap | тапнуть | — |
| to scroll | скроллить | — |
| to pinch / zoom | сделать pinch / zoom | — |
| to onboard | онбордить (пользователя) | — |
| to notify | отправить уведомление | — |
| to track (analytics) | отслеживать (аналитику) | — |
| to monetize | монетизировать | — |
| to sideload | сайдлоадить (установить APK мимо магазина) | — |

## Раздел 17. Падежные формы (для переводчиков)

### Activity / Fragment / Intent / ViewController

**Не склоняются** в качестве имён системных компонентов. «Создать Activity», «передать Intent», «открыть ViewController». В разг. речи допустимо: «активити», «фрагмент» (склоняется как обычное существительное).

### Swift / Kotlin / Java / Objective-C / Dart

**Не склоняются.** «На Swift», «через Kotlin», «с Java», «на Dart». «На Котлине» — разг.

### iOS / Android / macOS / watchOS / iPadOS

**Не склоняются.** «В iOS», «для Android», «под macOS». НЕ «в иОСе», «под Андроидом» — в разговорной речи допустимо «Андроид».

### Виджет / Корутина / Композабл

- **Виджет** (м.р.): виджета, виджету, виджетом
- **Корутина** (ж.р.): корутины, корутину; мн.ч. корутины, корутин
- **Композабл** (м.р.): композабла, композаблу; мн.ч. композаблы, композаблов

### APK / AAB / IPA / SDK / NDK / APNs / FCM / IAP / MDM

**Не склоняются.** «Собрать APK», «загрузить AAB», «через SDK». В составных — через дефис: «APK-файл», «SDK-вызов», «MDM-политика».

### React Native / Flutter / Xamarin / Expo / KMM

**Не склоняются.** «На React Native», «с Flutter», «через KMM».

### App Store / Google Play / RuStore

**Не склоняются.** «В App Store», «через Google Play», «в RuStore».

## Раздел 18. Типовые ошибки переводчика (для переводчиков)

### 1. Перевод имён ОС

```
✗ «иОС», «Андроид»
✓ «iOS», «Android»
```

В разговорных текстах допустимо «Андроид» — устоявшийся вариант. В технических — оригинал.

### 2. Перевод имён языков

```
✗ «свифт», «котлин», «дарт»
✓ «Swift», «Kotlin», «Dart»
```

В разговорной речи «котлин», «свифт» — допустимо.

### 3. Перевод имён системных компонентов

```
✗ «активность», «намерение», «представление-контроллер»
✓ «Activity», «Intent», «ViewController»
```

Имена системных классов — оригинал.

### 4. Перевод полей и API

```
✗ «представление», «модель представления»
✓ «View», «ViewModel»
```

`ViewModel` — конкретный Android-класс, не переводится.

### 5. Bundle (Android) ≠ Bundle (Web)

В Android `Bundle` — контейнер данных для передачи между Activity. Не путать с веб-bundle (бандл, сборка).

### 6. Service (Android) ≠ Service (Web)

Android `Service` — фоновый компонент приложения. Не путать с веб-сервисом или K8s Service.

### 7. Widget (iOS) ≠ Widget (Flutter)

- iOS Widget — мини-приложение на экране (через WidgetKit)
- Flutter Widget — единица UI (StatelessWidget, StatefulWidget)
- Android App Widget — аналог iOS Widget

Контекст важен. При переводе сохраняй контекст оригинала.

### 8. «Приложение» vs «программа» vs «софт»

В мобильной разработке — **приложение** (app). «Программа» режет глаз, «софт» — разговорное.

### 9. Калька «является приложением»

```
✗ «MyApp является нативным приложением для iOS»
✓ «MyApp — нативное приложение для iOS»
```

### 10. «Платформа» vs «ОС»

`Platform` обычно = ОС в контексте мобильной разработки. Допустимо «iOS», «Android», «iOS / Android платформы». Иногда `platform` = весь стек (Apple platform = iOS + iPadOS + macOS + watchOS + tvOS + visionOS).

### 11. Push notification → «push-уведомление»

Через дефис, склоняется: push-уведомления, push-уведомлению.

### 12. App Store не склоняется

```
✗ «в Аппсторе», «в Эппсторе»
✓ «в App Store»
```

### 13. iPhone / iPad / Mac — оригинал

```
✗ «айфон», «айпад», «мак»
✓ «iPhone», «iPad», «Mac»
```

В разговорных текстах допустимо «айфон», «айпад».

## Раздел 19. Чек-лист + источники

### Чек-лист переводчика

- [ ] **Имена ОС** (iOS, iPadOS, macOS, watchOS, tvOS, visionOS, Android, Wear OS, HarmonyOS) — оригинал
- [ ] **Имена языков** (Swift, Kotlin, Java, Objective-C, Dart, C++) — оригинал
- [ ] **Имена фреймворков** (SwiftUI, UIKit, Jetpack Compose, React Native, Flutter, KMP/KMM) — оригинал
- [ ] **Имена системных компонентов** (Activity, Fragment, Intent, ViewController, Service, BroadcastReceiver, ContentProvider, Bundle) — оригинал
- [ ] **Имена API** (CoreData, ARKit, MLKit, CameraX, WorkManager, Room, Combine) — оригинал
- [ ] **Имена магазинов** (App Store, Google Play, **RuStore, NashStore**, AppGallery) — оригинал
- [ ] **Аббревиатуры** (SDK, NDK, IDE, APK, AAB, IPA, APNs, FCM, IAP, ASO, MDM, BYOD, ANR, FPS, GMS, AOSP) — оригинал, расшифровка при первом упоминании
- [ ] **iPhone / iPad / Mac / Apple Watch / iPad** — оригинал
- [ ] **Имена устройств** — оригинал
- [ ] **«Приложение»** вместо «программа» / «софт»
- [ ] **«Браузер», «компонент», «активность» — НЕ для системных классов** (Activity, Component в RN)
- [ ] **Калек избегли** — нет «является»
- [ ] **Кавычки** — «ёлочки»
- [ ] **Push-уведомление через дефис**
- [ ] **Российская специфика** (RuStore, AppMetrica, MyTracker, Аврора ОС, ЕБС) — точные русские названия

### Источники

| Источник | Назначение |
|----------|-----------|
| Apple Developer Docs — https://developer.apple.com/documentation/ | Эталон для iOS / SwiftUI / UIKit |
| Android Developer Docs — https://developer.android.com/ | Эталон для Android / Jetpack Compose |
| Kotlin docs (RU) — https://kotlinlang.ru/ | Русская локализация Kotlin |
| React Native Docs — https://reactnative.dev/ | RN |
| Flutter Docs — https://docs.flutter.dev/ | Flutter |
| Сбер / VK / Avito / Yandex Mobile на Хабре | Российская мобильная разработка |
| MOBIUS-конференции — https://mobiusconf.com/ | Доклады по iOS/Android |
| **RuStore Developer** — https://www.rustore.ru/developers/ | Российская специфика магазинов |
| **AppMetrica Docs (Yandex)** | Российская мобильная аналитика |
| **MyTracker Docs (VK)** | Российская мобильная аналитика |
| Альянс ПРО (tran.su) | Методология |

Версия: **2026-05-16 v1.0**.

## Связь с другими словарями

- **Mobile + Networking** — статья про мобильные сети, латентность 5G, WebSocket в RN → mobile + networking
- **Mobile + Security** — статья про certificate pinning, jailbreak detection, MDM, биометрию → mobile + security
- **Mobile + DevOps** — статья про Fastlane, Bitrise, mobile CI/CD → mobile + devops
- **Mobile + ML/AI** — статья про on-device ML (CoreML, ML Kit), AI-чат в мобильном приложении → mobile + ml-ai
- **Mobile + Frontend** — статья про React Native + Web (Expo Web), Capacitor, общий код между Web и Mobile → mobile + frontend

Приоритеты при конфликте — в `translation-standards.md`.

## Использование вне модуля перевода

Этот словарь подключается не только субагентами `article-translation-agent`, но и любыми авторами/редакторами русскоязычного мобильного контента (SEO-статьи про мобильную разработку, документация RuStore SDK, пресс-релизы мобильных продуктов, дайджесты мобильных новостей). Чтобы подключить словарь к другому субагенту, добавь в его frontmatter:

```yaml
skills:
  - mobile-translation-dictionary
```

Активация — автоматическая по триггерам (см. `activation:` в начале файла).
