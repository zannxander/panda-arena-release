# Changelog

## 0.6.3

### Battle Replays

- Slowed replay playback so the previous 0.25x timing is now the new 1x baseline.
- Updated the 0.5x, 1x, 2x, and 4x controls to use consistent action intervals of 4, 2, 1, and 0.5 seconds.
- Refreshed replay rules compatibility after the card-rule corrections in this release.

### Cards And Rules

- Fixed `CT-P09-109` Kaito Kid & Toru Amuro so its same-level, same-name deck reveal can find `CT-P10-038` Kaito Kuroba through the Kaito Kid name it also has in the deck.
- Preserved additive card-name identity: `CT-P10-038` remains Kaito Kuroba while also being treated as Kaito Kid in the deck and remove area.
- Fixed characters printed to enter the field asleep so their entry state is applied consistently, including `PR186`.
- Separated rules-level hand reveals from cards that are only shown as part of another action, preventing unrelated reveal triggers from activating.
- Fixed effects that require a character to enter through one of the player's own character abilities so they verify the real effect source and owner.
- Fixed several reported effects involving solution-stage Flash targets, matching revealed levels, and contact-removal draw triggers.

### Stability And Testing

- Added focused regression coverage for the recent Bug 22 and Bug 23 reports, alternate printings, card-name aliases, reveal ownership, effect sources, and sleeping entry states.
- Passed the complete client E2E suite: 964 tests.
- Verified the Windows release launch, Android package metadata, release signing certificate continuity, and release-package isolation rules.

### Update Notes

- Windows: use `PANDA-0.6.3.zip`.
- Android: install `PANDA-0.6.3.apk`; it can be installed over 0.6.2 with the same signing certificate.
- No room-server update is required for this client release.
- Replays recorded with an older rules fingerprint may be rejected as incompatible after these card-rule changes.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.

## 0.6.0

### Battle Replays

- Added local replay recording for completed local and online battles.
- At the end of a recorded match, choose whether to save it; unfinished save decisions can be recovered from the replay library.
- Added a replay library with playback, import, export, and deletion controls.
- Added pause, restart, step backward or forward, and 0.5x, 1x, 2x, and 4x playback speeds.
- Replay playback skips player thinking and network waiting time and advances at a fixed action interval.
- Added free switching between P0 and P1 perspectives while keeping only the selected player's private information visible.
- Replay mode is read-only and validates file integrity, rules and card compatibility, action order, and deterministic state.
- Preserved compatibility with replay files created during 0.6.0 development.

### Interface

- Added a Replays entry to the battle menu.
- Kept the battle entry menu touch-friendly with a two-column layout and no scrolling.
- Added English, Simplified Chinese, and Japanese replay interface text and visible errors for invalid or incompatible files.

### Stability And Testing

- Added replay recording, persistence, reconnect reconstruction, playback, compatibility, corruption, and UI regression coverage.
- Verified an existing 80-action replay from start to finish.
- Verified the Windows and Android release builds; Android uses the same signing certificate as 0.5.3.

### Update Notes

- Windows: use `PANDA-0.6.0.zip`.
- Android: install `PANDA-0.6.0.apk`; it can be installed over 0.5.3.
- No room-server update is required for this client release.
- Replay files can reveal both players' complete decks and private draw order when shared.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.

## 0.5.3

### Account Recovery

- Added a secure six-digit email-code flow for forgotten passwords.
- Added password-recovery entry points for both the login screen and locally saved accounts, without asking saved users to enter their email address again.
- Hardened recovery requests, one-time challenges, successful reset handling, and old-session invalidation.

### Decks And Interface

- Deck cards now default to level sorting from highest to lowest when the deck editor opens.
- Added a game-start sound and refined recent battle choice, board rendering, and trait-display behavior.

### Cards And Rules

- Fixed effects that look at three deck cards and select one so every unselected card moves to the remove area.
- Fixed an event effect that could be queued twice instead of resolving as one conditional effect.
- Fixed a hand-to-field effect so its required field discard must be a black character.
- Fixed the Azusa Enomoto kidnapping case effect so characters in every zone actually gain the Cafe Poirot trait for the turn, including cards in hand used by follow-up effects.
- Preserved generated CT-P10 rule semantics and corrected additional recently reported card-effect and trait-matching cases.

### Stability And Testing

- Expanded real player-flow regression coverage for password recovery, deck sorting, recent feedback reports, Android compatibility, and structured card effects.
- Verified the Windows and Android release builds against the full automated gameplay suite.

### Update Notes

- Windows: use `PANDA-0.5.3.zip`.
- Android: install `PANDA-0.5.3.apk`.
- The room server required for password recovery has already been updated; players do not need to perform any server-side action.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.

## 0.5.0

### New Cards And Rules

- Added the complete CT-P10 card set with structured effects, localized card data, product filtering, and broad player-flow E2E coverage.
- Added Promotion Pack Vol.14 cards and their alternate-print identities without bundling official card images.
- Fixed reported effect issues involving source zones, card-name and trait matching, optional branches, play states, contact follow-ups, FILE and remove-area interactions, and granted abilities.
- Improved structured effect labels so declaration choices and multi-branch effects are easier to distinguish during play.

### Game Flow And Interface

- Added a synchronized rock-paper-scissors step before the opening mulligan, with simultaneous reveal, tie retries, and reusable card-effect support.
- Added distinct gesture icons and clearer choice-state handling so one player's confirmation cannot erase the other player's draft selection.
- Improved pending-effect and selection-window summaries, including clearer branch labels and consistent return-to-table behavior.
- Fixed several reported selection-window cases so legal and illegal candidates are displayed and resolved consistently.

### Android

- Added an Android document-provider import bridge for card-image ZIP files and individual images, improving compatibility with newer Android privacy and storage restrictions.
- Preserved compatibility with older supported Android versions and existing imported image libraries.
- Kept development E2E components, test scenes, server files, and official visual resources out of exported clients.

### Stability And Testing

- Expanded full player-flow E2E coverage for CT-P10, Promotion Pack Vol.14, recent feedback reports, shared rock-paper-scissors, Android image import, and effect-button labels.
- Updated runtime rule snapshots and structured effect generation to keep alternate printings and future cards on the same shared mechanics.

### Update Notes

- Windows: use `PANDA-0.5.0.zip`.
- Android: install `PANDA-0.5.0.apk`.
- Online play requires the room server to be updated for the synchronized pregame rock-paper-scissors flow.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.

## 0.3.1

### Engine And Compatibility

- Migrated the Windows and Android clients to Godot 4.7 while preserving the existing gameplay and online protocol.
- Kept card images as external player-provided resources and excluded development E2E fixtures from release packages.
- Improved alternate-print image identity so a missing PR or alternate artwork uses the localized placeholder instead of borrowing another printing's image.

### Cards And Rules

- Added the latest PR card batch and alternate-print identities, including localized card data and structured effect support.
- Fixed several reported card-effect issues involving card-name identity, temporary name changes, attached or granted declare abilities, choice scopes, and follow-up effects.
- Corrected dual-turn cut-in effects so their AP bonus changes properly between the player's turn and the opponent's turn.
- Corrected effects that require revealing an exact number of cards and refined optional target selection behavior.

### Decks And Interface

- Improved multi-feature deck searches and official banlist warnings, including clearer banned and limited-card markers.
- Added structured deck statistics for Flash, Cut-in, and Disguise cards.
- Improved cloud deck draft uploads, accessory-scheme management, and persistent online connection indicators.
- Restored card-detail access for FILE, evidence, and remove zones on desktop and Android.

### Android Experience

- Restored touch scrolling in card-detail and battle-effect windows.
- Increased touch-scroll responsiveness and kept short-tap selection separate from long-press card details.

### Update Notes

- Windows: use `PANDA-0.3.1.zip`.
- Android: install `PANDA-0.3.1.apk`.
- No room-server update is required for this client release.
- This release does not include official card image resources. Players still need to provide local card images or import image packs in the client.

## 0.2.3

### Online Play

- Updated the Windows, Android, and room-server version to `0.2.3`.
- Fixed matchmaking and profile flow routing after the recent battle-network split.
- Kept the server protocol compatible with the current `net-1` online play flow.

### Rules And Card Effects

- Improved structured card-name identity handling for effects that care about declared names, treated-as names, and temporary name changes.
- Fixed several reported same-root card effect issues around attached/granted declare abilities, contact display, choice scopes, and public deck warning labels.
- Improved display and filtering for choice windows so illegal or unavailable choices are handled consistently.

### Mobile Experience

- Fixed Android touch behavior in action-variant windows so short taps select cards and long presses open card details without conflicting.
- Kept Android release signing compatible with previous signed builds.

### Interface And Maintenance

- Continued the battle view split into focused controllers for room flow, matchmaking flow, action panels, card details, choice popups, logs, and HUD widgets.
- Added regression checks for the latest reported card-effect cases, mobile touch handling, deck warning labels, and selection-window display scope.

### Update Notes

- Windows: use `PANDA-0.2.3.zip`.
- Android: install `PANDA-0.2.3.apk`.
- Online play requires the room server to be updated to `0.2.3`.
- This release does not include official card image resources. Players still need to provide local card images or import image packs in the client.

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
