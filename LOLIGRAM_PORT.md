# Loligram for iOS

This branch is based on Telegram-iOS 11.5.3 from December 2024. It deliberately
uses the pre-Liquid-Glass Telegram interface as the visual baseline.

## Current port status

- The application display name is `Loligram`.
- The original Loligram web-player assets are bundled into the application.
- GitHub Actions can build an unsigned IPA for installation with AltStore.
- The native Swift bridge between Telegram media and the bundled player is the
  next implementation stage; bundling the files alone does not expose a player
  screen yet.

## CI secrets

Add these repository Actions secrets before starting the workflow:

- `TELEGRAM_API_ID`
- `TELEGRAM_API_HASH`

Create both values for your own application at <https://my.telegram.org/apps>.
Do not commit them to the repository.

Run **Actions → Build Loligram IPA → Run workflow**. When the job succeeds,
download the `Loligram-unsigned-ipa` artifact and install it with AltStore.
