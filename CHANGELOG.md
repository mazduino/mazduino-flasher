# Changelog

Versions follow `major.minor.patch`.

## 1.0.0 — 2026-11-11

First public build, for macOS on Apple Silicon.

### Mazduino ECU
- Finds the ECU on USB, reads which board it is and writes a published release for it, or your own `.bin` / `.hex`
- Puts the ECU into update mode by itself; an ECU already in update mode is picked up as it is
- Only Mazduino ECUs are offered as ports, so other USB devices are not mixed in

### Racedash
- Pick the dash by model, then update over USB or over the dash's WiFi
- Update firmware keeps settings; Full flash over USB writes everything
- Firmware comes from your Mazduino account

### CAN IO Extender
- Writes a published release for the board's crystal and CAN node

### App
- Status, progress and activity on the right, in the look of the Racedash dashes
- Plain-language messages; the details go to the log file
- Send feedback or report a problem from the menu, with the log attached
- Downloads are only taken from Mazduino's own release pages and account, and the sign-in session is kept in the macOS Keychain
