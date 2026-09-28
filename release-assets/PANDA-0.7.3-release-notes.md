# PANDA 0.7.3

This release brings optional room clocks, tournament-ready observation for authorized organizers, and more informative replay playback. It also includes the 0.7.2 room-timer changes, which were not previously published in this release repository.

## Timed Rooms And Tournaments

- Hosts of manually created rooms can choose a 90, 180, 300, 600, or 900-second turn limit and a 20, 25, 30, 40, 50, or 60-minute match limit. Either clock may remain unlimited, and timing starts after both players finish mulligan.
- Tournament rooms support organizer-controlled creation, monitoring, and observation. Only an authorized organizer can override the players' ordinary viewing settings.
- An authorized organizer can switch between P0 and P1 and inspect the selected player's hand; ordinary spectators do not receive this override.
- The portable tournament manager and organizer credentials are distributed privately. They are not part of these public downloads.

## Battle Replays

- Replays made with another game version are attempted when the file format is valid. State validation still stops playback at a divergent action; not every historical replay is guaranteed to work.
- Recorded effect-choice windows can be shown during playback. The recorded choice is highlighted and brought to the front; inspecting cards or zones pauses playback until the details are closed.
- Normal `.pdr` files remain unencrypted for player playback and sharing. Encrypted bug-report data remains a separate system.

## Cards And Stability

- Fixed Soccer Shinichi's effect-choice loop when no attached ball is available, with related boundary checks for similar ball-transfer effects.
- Verified the current client with 1,291 automated Godot E2E cases, including legal three-language demonstration matches. These tests do not replace Android-device or native macOS testing.

## Downloads

- Windows: `PANDA-0.7.3.zip`
- Android: `PANDA-0.7.3.apk`
- macOS: `PANDA-0.7.3-macos.zip`

The Android APK uses the same release signing identity as earlier releases. The macOS ZIP contains Simplified Chinese, Japanese, and English first-launch instructions; the app is not Apple-notarized.

Timed rooms and tournament observation require a compatible updated room server. The server owner must enable the tournament service separately. Public client installation does not grant organizer access or change the owner's server settings.

This release contains no official card images. Players can add a local `card_images` folder or import an image pack in the client. PANDA is an unofficial, non-commercial fan-made simulator and is not affiliated with or endorsed by the original rights holders.

## SHA-256

```text
PANDA-0.7.3.zip        31C02B9F39ACDB7EB547C8C62AB66CEAE45E8C1A68D81C95242B79979C05064B
PANDA-0.7.3.apk        D1E021AACA3FCDBC1BD2B16D742314678530FB3C1E33749EEC3147EAEF28FC41
PANDA-0.7.3-macos.zip  6475383A5CBDC9F662A52791F8DB2276C1268D646359C8EA3CF7DFE330A01D7A
```
