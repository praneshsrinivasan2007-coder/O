# MandiSetu — Expo App

A React Native / Expo port of the MandiSetu prototype: price board, sell-produce
form, and a direct farmer-to-buyer marketplace with cart.

## 1. Run it locally

You'll need [Node.js](https://nodejs.org) (18+) installed.

```bash
npm install
npx expo start
```

This opens the Expo dev tools. From there:
- Press `i` to open in the iOS Simulator (Mac only, needs Xcode)
- Press `a` to open in an Android Emulator (needs Android Studio)
- Or scan the QR code with the **Expo Go** app on your own phone — fastest way
  to see it running on a real device with no setup

## 2. Customize

- `src/data.js` — crop list and seed farmer listings. Replace with a real API
  later (mandi price feed, your own backend for listings).
- `src/theme.js` — colors.
- `src/screens/` — one file per screen.
- `app.json` — app name, bundle identifiers (`com.yourcompany.mandisetu` —
  change this to your own), icon, splash screen.

## 3. Build a real installable app (no Mac/PC build machine needed)

Expo's **EAS Build** service builds the actual `.ipa` (iOS) and `.apk`/`.aab`
(Android) files in the cloud:

```bash
npm install -g eas-cli
eas login
eas build:configure
eas build --platform android   # produces an installable APK/AAB
eas build --platform ios       # requires an Apple Developer account ($99/yr)
```

## 4. Submit to the app stores

```bash
eas submit --platform android   # to Google Play Console
eas submit --platform ios       # to App Store Connect
```

You'll need:
- A **Google Play Developer** account ($25 one-time) for Android
- An **Apple Developer Program** account ($99/year) for iOS

## Notes / next steps

- The cart/checkout currently just simulates "sending a request" — wire it to
  a real backend (Firebase, Supabase, your own API) to persist listings and
  orders across sessions and users.
- Add authentication (farmer vs. buyer accounts) before going live.
- Replace the placeholder phone numbers with real contact/click-to-call
  (`Linking.openURL('tel:...')`) once you have real farmer data.
