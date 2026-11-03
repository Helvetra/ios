# Helvetra iOS

Native iOS app for [Helvetra](https://helvetra.ch), a privacy-first Swiss translation app. Translations run on [Apertus](https://www.apertus-ai.org/), the open Swiss language model, through the Helvetra API: [github.com/Helvetra/backend](https://github.com/Helvetra/backend) (its README explains how the model is prompted and checked).

## Features

- Translation with real-time auto-translate
- Swiss German dialect support (Zurich, Bern, Basel, Luzern, St. Gallen, Wallis)
- Language auto-detection
- Formality toggle (du/Sie, tu/vous, tu/Lei)
- Sign in with Apple, or email and password (the same account as on the web)
- StoreKit 2 in-app subscriptions. Server-side verification of App Store purchases is currently switched off on the backend while it is rewritten against Apple's certificate chain
- VoiceOver labels on the translation screen
- App interface in 4 languages (English, German, French, Italian); translation between 6 (those four plus Romansh and Swiss German)

## Tech Stack

- **Framework:** SwiftUI
- **Minimum:** iOS 18
- **Project:** generated with [XcodeGen](https://github.com/yonaskolb/XcodeGen) from `project.yml`
- **Auth:** Sign in with Apple or email and password, tokens in the Keychain
- **Payments:** StoreKit 2
- **Architecture:** MVVM with ObservableObject services

## Setup

1. Open `Helvetra.xcodeproj` in Xcode (built and tested with Xcode 26)
2. Select your development team in Signing & Capabilities
3. Build and run on simulator or device

`Helvetra.xcodeproj` is generated from `project.yml`. After changing targets, files or build settings there, regenerate it with `xcodegen generate`.

The app talks to the production API at `https://helvetra.ch/api/v1`.

For StoreKit testing, the `Helvetra.storekit` configuration is included for local sandbox testing.

## Project Structure

```
Sources/Helvetra/
├── App/             # App entry point
├── Views/           # SwiftUI views
├── Services/        # Business logic (Auth, Store, Usage)
├── DesignSystem/    # Colors, typography, spacing
└── Resources/       # Assets and Info.plist
```

## About

Built by Alex Margot with [Claude Code](https://claude.com/claude-code), reviewed and tested by hand. Issues and questions: gruezi@helvetra.ch.

## License

MIT
