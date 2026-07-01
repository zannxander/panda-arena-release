# Changelog

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
