## About

This project is a **full-featured mobile banking UI** that replicates the look and feel of the National Bank of Egypt app. It demonstrates modern React Native development practices including atomic design, drawer & tab navigation, dark/light theming, OTP verification, biometric authentication UI, drag-and-drop interactions, and map integration.

---

## Features

### Authentication

- Login with username & password
- Fingerprint / biometric authentication UI
- "Remember Me" functionality
- New user signup with Egyptian phone number validation
- OTP phone verification
- Set password with validation conditions
- Success confirmation screen

### Home Dashboard

- Animated balance card with fingerprint verification
- Credit cards carousel with card details (holder, number, expiry, CVV)
- Quick-access services grid
- Send money to recent contacts
- Transaction history

### Transfers

- Transfer between own accounts
- Transfer to another account
- Account picker dropdowns
- Amount & reason inputs
- OTP confirmation for transfers
- Transfer success modal

### Beneficiaries

- Horizontal quick-access list
- Vertical full list with search
- Add new beneficiary (name, phone, image)
- Drag-and-drop reordering via `react-native-drax`
- Per-beneficiary transaction history

### ATM Locator

- Interactive MapView centered on Cairo
- ATM location markers with details

### Settings (Drawer)

- Dark / Light theme toggle (persisted via Context)
- Account summary
- Certificates & deposits
- Payment & card services
- Offers
- Logout

---

## Screenshots

> Add your own screenshots here.

| Splash | Login | Home | Transfer | Beneficiaries | ATMs | Settings |
| ------ | ----- | ---- | -------- | ------------- | ---- | -------- |
|        |       |      |          |               |      |          |

---

## Tech Stack

| Category     | Technology                                                                                          |
| ------------ | --------------------------------------------------------------------------------------------------- |
| Framework    | [React Native](https://reactnative.dev/) 0.74.1                                                     |
| Language     | [TypeScript](https://www.typescriptlang.org/) 5.0                                                   |
| Navigation   | [React Navigation](https://reactnavigation.org/) — Stack, Bottom Tabs, Drawer                       |
| Maps         | [react-native-maps](https://github.com/react-native-maps/react-native-maps)                         |
| Animations   | [React Native Reanimated](https://docs.swmansion.com/react-native-reanimated/) 3.11                 |
| Icons        | [FontAwesome](https://fontawesome.com/) (Solid & Regular) via `react-native-fontawesome`            |
| Drag & Drop  | [react-native-drax](https://github.com/nuclearpasta/react-native-drax) + Gesture Handler            |
| OTP Input    | [react-native-otp-textinput](https://github.com/AkashMishra/react-native-otp-textinput)             |
| Image Picker | [react-native-image-picker](https://github.com/react-native-image-picker/react-native-image-picker) |
| SVG          | [react-native-svg](https://github.com/software-mansion/react-native-svg)                            |
| Linting      | ESLint + Prettier                                                                                   |
| Testing      | Jest + React Test Renderer                                                                          |

---

## Project Structure

The component architecture follows the **Atomic Design** pattern:

```
NBE/
├── App.tsx                        # Root — stack navigator, theme context, status bar
├── index.js                       # Entry point
├── assets/
│   ├── fonts/                     # Gemunu Libre (Bold, Regular)
│   └── images/                    # Logos, backgrounds, card assets, profile images
├── components/
│   ├── atoms/                     # Smallest UI elements
│   │   ├── CustomButton.tsx       #   Reusable button
│   │   ├── CustomInput.tsx        #   Styled text input
│   │   ├── CustomIcon.tsx         #   FontAwesome icon wrapper
│   │   ├── LoginInput.tsx         #   Auth-specific input
│   │   ├── MobileInput.tsx        #   Phone number input
│   │   ├── FingerPrint.tsx        #   Biometric auth UI
│   │   ├── Person.tsx             #   Beneficiary avatar item
│   │   ├── Service.tsx            #   Service grid item
│   │   ├── Picker.tsx             #   Dropdown picker
│   │   ├── SettingsItem.tsx       #   Settings row item
│   │   ├── TabBarIcon.tsx         #   Bottom tab icon
│   │   └── ...
│   ├── molecules/                 # Composed atom groups
│   │   ├── BalanceCard.tsx        #   Balance display card
│   │   ├── CreditCard.tsx         #   Credit card component
│   │   ├── LoginHeader.tsx        #   Auth header
│   │   ├── LoginFooter.tsx        #   Auth footer
│   │   ├── ServicesContainer.tsx  #   Services grid
│   │   ├── PersonContainer.tsx    #   Send money contacts
│   │   ├── HistoryContainer.tsx   #   Transaction history
│   │   ├── SettingsContent.tsx    #   Settings menu items
│   │   └── ...
│   ├── organisms/                 # Complex UI sections
│   │   ├── LoginForm.tsx          #   Complete login form
│   │   ├── TransferModal.tsx      #   Transfer confirmation modal
│   │   ├── CreditCardsContainer.tsx
│   │   ├── BeneficiariesHorizontalList.tsx
│   │   ├── BeneficiariesVerticalList.tsx
│   │   └── SettingsContainer.tsx
│   ├── pages/                     # Full screens
│   │   ├── Main.tsx               #   Bottom tab navigator
│   │   ├── DrawerMain.tsx         #   Drawer layout
│   │   ├── Auth/                  #   Login, Signup, Verification, SetPassword, Success
│   │   ├── Home/                  #   Balance, CreditCards
│   │   ├── Transfer/              #   TransferForm, OtpTransfer
│   │   ├── Beneficiaries/         #   Main, History, Add
│   │   ├── ATMs/                  #   ATM map screen
│   │   └── Splasher/              #   Splash screen
│   └── templates/
│       └── OTPTemplate.tsx        #   Reusable OTP verification layout
├── android/                       # Android native project
├── ios/                           # iOS native project (CocoaPods)
└── __tests__/                     # Jest test files
```

---

## Prerequisites

- **Node.js** >= 18
- **npm** or **yarn**
- **Ruby** (for CocoaPods on iOS)
- **Xcode** (iOS builds — macOS only)
- **Android Studio** (Android builds)
- **CocoaPods** (`gem install cocoapods`)

---

## Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/NBE.git
cd NBE

# 2. Install dependencies
npm install

# 3. Install iOS pods (macOS only)
cd ios && pod install && cd ..

# 4. Start Metro bundler
npm start

# 5. Run on a platform
npm run ios        # iOS
npm run android    # Android
```

---

## Available Scripts

| Command           | Description                     |
| ----------------- | ------------------------------- |
| `npm start`       | Start the Metro bundler         |
| `npm run ios`     | Build & run on iOS simulator    |
| `npm run android` | Build & run on Android emulator |
| `npm run lint`    | Run ESLint across the project   |
| `npm test`        | Run Jest test suite             |

---

## Custom Fonts

The app uses the **Gemunu Libre** font family (Bold & Regular), linked via `react-native.config.js`:

```js
module.exports = {
  assets: ['./assets/fonts'],
};
```

Fonts are auto-linked at build time. On Android they are copied to `android/app/src/main/assets/fonts/`, and on iOS they are registered in `Info.plist`.

---

## Theme Support

The app supports **dark and light modes** via a React Context (`ThemeContext`). The toggle is available in the settings drawer. Theme-aware colors are applied across all screens and navigation elements.

| Light Mode                | Dark Mode                 |
| ------------------------- | ------------------------- |
| `#F1F3FB` background      | `#121212` background      |
| `#1C2437` text            | `#FFFFFF` text            |
| Green accents (`#007236`) | Green accents (`#007236`) |

---

## Disclaimer

> This project is a **UI clone built for educational and portfolio purposes only**. It is **not affiliated with, endorsed by, or connected to the National Bank of Egypt** in any way. No real banking functionality is implemented — all data is static/mock. Do not use this project to impersonate or misrepresent any financial institution.
