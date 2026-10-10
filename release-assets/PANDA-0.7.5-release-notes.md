# PANDA 0.7.5

This release adds the October PR cards, fixes original-ability suppression and alternate-art selection, and adds a convenient Copy Deck Code button. It also includes the 0.7.4 card-rule fixes, which were not previously published as a GitHub Release in this repository.

## New PR Cards

- Added PR324–PR338: 15 printings, including alternate artwork, across nine rules families.
- Verified that all 15 printings are present in the actual Windows, Android, and macOS release packages, not just in a separate development branch.

## Card And Artwork Fixes

- Fixed Kazuha's original-ability suppression so printed abilities such as Mislead correctly stop working while suppressed. Abilities granted by other cards and effects that have already resolved are preserved.
- Fixed selected alternate artwork changing when a card enters a battle. The fix covers 14 affected card families, including Shinichi & Conan, level 8 Sera, and level 8 Takaaki, and preserves the chosen printing in deck codes and replay data.
- Includes the 0.7.4 fixes for Swift during an opponent's turn, Mislead target selection, attached-event leave timing, and the affected sleep-then-draw effect branch.

## Deck Editor

- Added Copy Deck Code beside Export Deck Code in the main deck editor, and beside Save in the room deck editor.
- Copies the current deck, including unsaved edits and selected artwork, with cards ordered from highest level to lowest.
- Includes Simplified Chinese, Japanese, and English interface text.

## Downloads

- Windows: `PANDA-0.7.5.zip`
- Android: `PANDA-0.7.5.apk`
- macOS: `PANDA-0.7.5-macos.zip`
- File verification: `PANDA-0.7.5-SHA256SUMS.txt`

The Android APK retains the previous release signing identity. The macOS build supports both Intel and Apple Silicon; its ZIP preserves executable permissions and includes Simplified Chinese, Japanese, and English first-launch instructions. The macOS app is not Apple-notarized, and native Mac execution was not tested on the Windows build machine.

Official card images are not included in these public downloads. Keep your existing user-provided `card_images` folder or import compatible local images in the client. Newly added cards require matching local images to display their artwork.

This publication does not update the production room server, change tournament permissions, or distribute the private tournament manager or organizer credentials. Those are managed separately by the server owner.

## Validation

- New PR coverage: 75 passed; original-ability suppression: 157 passed; printing identity: 488 passed.
- Required release regressions: 63 passed; integration and packaging unit checks: 29 passed.
- The full Godot E2E run passed 2,149 of 2,151 cases. Two Windows clipboard-log failures were retained in the report; the complete 37-case copy/UI rerun then passed.

These automated checks do not replace Android-device or native macOS testing, and do not claim to cover every unrelated effect of every card.

PANDA is an unofficial, non-commercial fan-made simulator and is not affiliated with or endorsed by the original rights holders.

## SHA-256

```text
PANDA-0.7.5.zip        3B29CB10D5360AC1D9EEB74289963EC7477B41889658E2F19118AE643A1837F4
PANDA-0.7.5.apk        853319F4EF9D1D0A8A48F0A690A13F9031671A3D1AE0D0C97CF6C673BB74A919
PANDA-0.7.5-macos.zip  52768D8544BCE1342D2DDD824C0C40FE8F91BBAD4C5996CD5EC1495CED8F0914
```
