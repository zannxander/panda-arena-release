# Changelog

## 0.2.2

### Online Play

- Updated the Windows, Android, and room-server version to `0.2.2`.
- Fixed matchmaking routing after the battle UI split so matchmaking actions enter the correct flow again.
- Improved matchmaking profile display and room/match flow behavior after recent network UI refactors.
- Increased room spectator capacity to 5 seats.
- Improved spectator and player name display during online games.

### Mobile Experience

- Fixed Android touch handling in cut-in/disguise selection windows: short taps select a candidate, long presses open card details, and selection still requires confirmation.
- Kept Android release signing compatible with the previous release so the APK can be installed over `0.2.1`.

### Rules And Card Effects

- Improved structured card-name identity handling for card-name based effects, including cards that change or are treated as another card name.
- Fixed several same-root card effect issues caused by name matching and target filtering after the name-key migration.
- Fixed cut-in AP identity filtering so effects that check AP-gaining cut-in cards handle turn-restricted or no-effect cut-ins correctly.
- Refined several reported card effect and target-selection cases from recent bug reports.

### Interface And Decks

- Continued splitting the battle view into focused UI controllers for action panels, choice popups, card details, HUD, logs, room flow, and matchmaking flow.
- Fixed deck legality messages so incomplete or invalid deck warnings use public card names instead of internal IDs.
- Fixed fullscreen dropdown sizing so option lists no longer expand to the whole screen.
- Updated the Windows package to include an empty `card_images/` folder for local image resources.

### Stability And Testing

- Added regression checks for mobile cut-in/disguise touch behavior, choice display scope, public deck warning labels, and reported bug cases.
- Refreshed server version checks and release assets for Windows and Android.

### Update Notes

- Windows: use `PANDA-0.2.2.zip`.
- Android: install `PANDA-0.2.2.apk`.
- Online play requires the room server to be updated to `0.2.2`.
- This release does not include official card image resources. Players still need to provide local card images or import image packs in the client.

## 0.2.1

### Online Play

- Streamlined matchmaking so matched games enter battle directly instead of going through the room preparation screen.
- Improved matchmaking reconnect prompts: players are now asked about reconnecting before choosing a deck again.
- Fixed stale actions after reconnects that could cause multiple turns to be skipped unexpectedly.
- Matchmaking games now return to the battle menu after the game ends instead of offering room-only preparation options.
- Room ownership now follows the earliest remaining player in the room, with a visible host marker.
- Unrestricted room mode now only skips the official banlist check. Basic deck legality such as deck size, partner/case counts, and copy limits is still enforced.

### Client And UI

- Added Windows fullscreen support, including the settings option and `F11` toggle.
- Improved card name search in deck editors and room deck editors, including simplified Chinese name corrections such as Subaru Okiya.
- Updated release export rules so local audit files, development tools, and official visual resources are not bundled.

### Rules And Card Effects

- Corrected cut-in timing behavior: cut-in cards can still be used outside their effective turn condition, but produce no effect when the official condition is not met.
- Fixed several multi-color partner/case filters so color requirements apply to activation conditions without incorrectly expanding effect targets.
- Fixed color and condition filters for several search, reveal, and play-from-deck effects.
- Fixed contact context after Rye cut-in so follow-up play effects can resolve correctly.
- Fixed Iori Muga contact-removal follow-up so it enters pending and can play Momiji Ooka from the remove area.
- Fixed duplicate enter effects on Edogawa Conan.
- Fixed several same-root card effect issues reported around Azusa Enomoto and Takaaki Morofushi.
- Corrected a simplified Chinese card name typo for Natsuki Koshimizu.

### Stability And Testing

- Added and refreshed regression scripts covering server checks, deck legality, disconnect/reconnect flow, banlist validation, cut-in timing, search behavior, and reported card-effect cases.
- Added release note generation tooling for future public and internal changelog drafts.

### Update Notes

- Windows: use `PANDA-0.2.1.zip` or `PANDA-0.2.1/PANDA.exe`.
- Android: install `PANDA-0.2.1.apk`.
- Online play requires the room server to be updated to `0.2.1` for matchmaking, reconnect, and deck-legality behavior to match the client.
- This release does not include official card image resources. Players still need to provide local card images or import image packs in the client.

## 0.1.1

- Added account support and cloud deck slots.
- Added official banlist validation and room-host unrestricted mode.
- Improved room host handling, spectator/reconnect flows, and server diagnostics.
- Added external BGM assets and updated Windows / Android release exports.
- Continued card effect and structured rule fixes.

## 0.1.0

- First public release package for Windows and Android.
- Card images are external resources and are not bundled here.
- macOS builds are not included in this release repository.
