# Loligram for iOS

This branch is based on Telegram-iOS 11.5.3 from December 2024. It deliberately
uses the pre-Liquid-Glass Telegram interface as the visual baseline.

## Current port status

- The application display name is `Loligram`.
- The original Loligram web-player assets are bundled into the application.
- GitHub Actions can build an unsigned IPA for installation with AltStore.
- Sideloaded builds disable iCloud and Siri capabilities because their
  containers belong to Telegram's App Store signing identity. Enabling iCloud
  in a re-signed build causes CloudKit to terminate the app at launch.
- Settings exposes a native Music shortcut backed by Telegram's global music
  search and existing iOS player. This keeps the classic iOS interface while
  providing the Android fork's cross-chat music-library behavior.
- Sponsored messages are disabled at the engine boundary: Loligram neither
  requests them nor restores previously cached sponsored entries.
- Telegram iOS already provides native message translation, voice-message
  transcription, MTProto/SOCKS5 proxies, alternate icons, playback queues,
  seeking, speed, shuffle and repeat. These features stay on their native iOS
  implementations instead of duplicating Android UI code.

## CI secrets

Add these repository Actions secrets before starting the workflow:

- `TELEGRAM_API_ID`
- `TELEGRAM_API_HASH`

Create both values for your own application at <https://my.telegram.org/apps>.
Do not commit them to the repository.

Run **Actions → Build Loligram IPA → Run workflow**. When the job succeeds,
download the `Loligram-unsigned-ipa` artifact and install it with AltStore.
