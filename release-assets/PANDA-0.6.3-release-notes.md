# PANDA 0.6.3

This release slows replay playback and fixes another group of reported card-rule issues involving card-name aliases, hand reveals, entry states, effect sources, Flash targets, and contact triggers.

## Battle Replays

- The previous 0.25x timing is now the new 1x playback baseline.
- Replay speeds now advance at approximately 4 seconds per action at 0.5x, 2 seconds at 1x, 1 second at 2x, and 0.5 seconds at 4x.
- Replay playback still skips player thinking and network waiting time.

## Card And Rules Fixes

- Fixed `CT-P09-109` Kaito Kid & Toru Amuro so it can find `CT-P10-038` Kaito Kuroba as a level 8 Kaito Kid while that card is in the deck.
- `CT-P10-038` continues to keep its printed Kaito Kuroba name while also being treated as Kaito Kid in the deck and remove area.
- Fixed characters that are printed to enter the field asleep, including `PR186`.
- Prevented cards that are only shown during another action from incorrectly counting as rules-level hand reveals.
- Corrected effects that require entry through one of the player's own character abilities so they check the real source and owner.
- Corrected additional reported effects involving solution-stage Flash targets, matching revealed levels, and contact-removal draw triggers.

## Downloads

- Windows: `PANDA-0.6.3.zip`
- Android: `PANDA-0.6.3.apk`

The Android APK can be installed over 0.6.2 and uses the same signing certificate. No room-server update is required for this release.

## Important Notes

- Replays recorded with an older rules fingerprint may be rejected as incompatible after the card-rule updates in this release.
- This release does not include official card images. Players still need to provide local card images or import image packs in the client.
- PANDA is an unofficial, non-commercial fan-made simulator and is not affiliated with or endorsed by the original rights holders.

## SHA-256

```text
PANDA-0.6.3.zip  A54E3CF2C988673018412C71F84F60F29E8F8472FCC3E3F0C4E0F2396E90534F
PANDA-0.6.3.apk  F35CE0751EACB29B592E420885AA8A0D09A43521EC5064230349188450DC94CA
```
