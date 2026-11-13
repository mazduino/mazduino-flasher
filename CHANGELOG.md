# Changelog

Versions follow `major.minor.patch`; `-alpha.N` and `-beta.N` are test builds.

## 0.1.0-alpha.2 — 2026-11-13

### Racedash
- The dash is read as soon as it is plugged in: its model comes from the firmware on it, so there is no model to pick and no way to pick the wrong one
- The M7 Pro's hardware revision is read from the dash too, and the matching firmware is chosen for it. It is no longer a choice
- A dash with no Mazduino firmware on it (new, erased, or running something else) is handled as a new dash: only the models built for its hardware are offered, and only a Full flash
- Over WiFi the dash is asked which model it is. A dash that does not say is updated over USB instead
- **Not this model?** treats a dash that was flashed with another model's firmware as a new dash
- The dash tab now starts with the connection, then shows what was found

## 0.1.0-alpha.1 — 2026-11-11

First public test build, for macOS on Apple Silicon. Windows follows in a later alpha.

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
