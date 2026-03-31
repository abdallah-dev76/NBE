## About

This project is a **full-featured mobile banking UI** that replicates the look and feel of the National Bank of Egypt app. It demonstrates modern React Native development practices including atomic design, drawer & tab navigation, dark/light theming, OTP verification, biometric authentication UI, and map integration.

---

## Features

### Authentication

- Login with username & password
- Fingerprint / biometric authentication UI
- New user signup with Egyptian phone number validation
- OTP phone verification
- Set password with validation conditions
- Success confirmation screen

### Home Dashboard

- Animated balance card
- Credit cards carousel with card details (holder, number, expiry, CVV)
- Quick-access services grid
- Send money to recent contacts
- Transaction history

### Transfers

- Transfer to another account
- Account picker dropdowns
- Amount & reason inputs
- OTP confirmation for transfers
- Transfer success modal

### Beneficiaries

- Horizontal and Vertical quick-access list
- Add new beneficiary (name, phone, image)

### ATM Locator

- Interactive MapView centered on Cairo
- ATM location markers with details

### Settings (Drawer)

- Dark / Light theme toggle (persisted via Context)
- Account summary
- Logout

---

## Demo
[Insert The Video Here]
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
| OTP Input    | [react-native-otp-textinput](https://github.com/AkashMishra/react-native-otp-textinput)             |
| Image Picker | [react-native-image-picker](https://github.com/react-native-image-picker/react-native-image-picker) |
| SVG          | [react-native-svg](https://github.com/software-mansion/react-native-svg)                            |
| Linting      | ESLint + Prettier                                                                                   |

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
