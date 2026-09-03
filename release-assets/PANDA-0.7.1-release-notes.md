# PANDA 0.7.1

This release adds encrypted replay snapshots for safer bug reports, improves mobile touch interaction and effect-window navigation, corrects card-name and reveal-return rules, and introduces a macOS build.

## Battle Replays And Bug Reports

- Bug reports can now copy an encrypted replay snapshot instead of exposing private match information as plain text.
- Normal `.pdr` replay files remain unencrypted and can still be saved, shared, imported, and played normally.
- Replay controls now stay in a collapsible drawer at the right edge of the battle screen.
- Android replay importing now uses the native document picker for readable file selection and access to downloaded files.

## Mobile And Interface

- Improved touch scrolling when a drag begins on a card, including target-selection windows.
- Separated touch taps, scrolling, dragging, and long presses from desktop mouse controls to prevent duplicate or conflicting actions.
- Added return-to-table and resume controls to more effect windows without resolving or changing the pending choice.
- Added a clear choose-none action for effects that officially allow selecting zero cards.

## Decks And Card Rules

- Deck codes now export main-deck cards by level from highest to lowest.
- Fixed temporary card-name replacement effects while preserving official additive name aliases in the zones where they apply.
- Fixed reveal-and-return effects so cards are reviewed and shuffled back without unnecessary manual ordering; effects that officially require ordering still keep it.

## Downloads

- Windows: `PANDA-0.7.1.zip`
- Android: `PANDA-0.7.1.apk`
- macOS: `PANDA-0.7.1-macos.zip`

The Android APK uses the same signing certificate as earlier signed releases. No room-server update is required for this release.

The macOS package is a universal build. Fully extract the ZIP before starting it and follow the included Simplified Chinese, Japanese, and English launch guide on first run.

## Important Notes

- Replays recorded with an older rules fingerprint may be rejected as incompatible after the card-rule corrections in this release.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.
- PANDA is an unofficial, non-commercial fan-made simulator and is not affiliated with or endorsed by the original rights holders.

## SHA-256

```text
PANDA-0.7.1.zip        1DCBAE7E1F4F1C99E599D541279B4CE3C16198A618B51E9852B8B2A15E5AB04A
PANDA-0.7.1.apk        11FF0404CDAC5B43DDB2A30B0D6E95AC964B16524E7FBD20E2F05D821C90BD10
PANDA-0.7.1-macos.zip  FFB599A7BA11A340D08BC3D2302DB4E20385AA14698E34AE57F239A16A480DA8
```
