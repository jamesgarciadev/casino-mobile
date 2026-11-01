# casino-mobile

**0dds.bet** for Android and iOS, one app from one codebase. **Status: not started.** This repo only holds this README
and the review config so far; everything below is the plan, not what exists.

## Planned tech stack

| Layer | Plan |
|---|---|
| Framework | [Expo](https://expo.dev) (latest SDK) with React Native, TypeScript |
| Navigation | expo-router (file-based routes), tabs: Home, Matches, Wallet and History, Profile, with the bet slip as a bottom sheet |
| API | The same GraphQL API as `casino-web`: `matches`, `wallet`, `myBets`, `placeBet`, `placeComboBet`, `cashOutBet`, `login` |
| Realtime | pusher-js to Laravel Reverb for the `matchUpdated` subscription |
| Look | "Crimson Heat" tokens from `../casino-design` as hex values, JetBrains Mono and Work Sans through `@expo-google-fonts` |
| Tests | Jest |

Android and iOS identifiers use `oddsbet`, because package and bundle names can't start with a digit. The designs to
follow are the Android home and iOS bet slip mockups in `../casino-design`.

## Prerequisites (for when it exists)

- Node.js 20.9 or newer and npm
- `casino-be` running with Reverb (see its README), and `casino-sim` if you want matches to move
- A phone with the Expo Go app, on the same network. A phone can't reach your computer as `localhost`, so the API URL
  will be your computer's LAN address.

There is no iOS Simulator on Windows (it needs Xcode on a Mac). Use Expo Go on an iPhone, or `npx expo start --web`. Store
builds later go through EAS cloud builds, which need an Apple Developer account for iOS.

## Start it up (intended, not working yet)

```sh
npm install
npx expo start      # scan the QR code with Expo Go
```
