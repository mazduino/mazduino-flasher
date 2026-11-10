# Mazduino Flasher

Desktop app for updating the firmware on Mazduino ECUs, Racedash dashes and the CAN IO Extender.

This repository holds the releases and the changelog. The source code is not public.

## Download

Get the latest build from [Releases](https://github.com/mazduino/mazduino-flasher/releases):
`MazduinoFlasher-<version>-macos.zip`.

- macOS 12 or newer, on an Apple Silicon Mac (M1 or later). Intel Macs are not supported yet.
- Nothing else to install. Everything the app needs to write firmware is inside it.
- Windows build: coming later.

### Opening it the first time

1. Unzip the download and move **Mazduino Flasher** to the Applications folder.
2. Open it. Builds are not notarised by Apple yet, so macOS says it cannot check the app.
   Click **Done**, then go to **System Settings › Privacy & Security** and click **Open Anyway**
   next to Mazduino Flasher.
3. Check that the file came from this repository's Releases page. Each release lists its SHA-256.

## What it does

**Mazduino ECU**
- Finds the ECU on USB and reads which board it is
- Writes a published [mazduino-fw](https://github.com/mazduino/mazduino-fw) release for that board,
  or your own `.bin` / `.hex`
- Puts the ECU into update mode by itself, with no jumper to set and no case to open
- An ECU that is already in update mode is picked up as it is

**Racedash**
- Pick the dash by model, then update it over the USB cable or over the dash's own WiFi
- **Update firmware** keeps the dash's settings. **Full flash** (USB only) writes everything and
  erases the settings.
- Firmware for dashes comes from your Mazduino account, so sign in first

**CAN IO Extender**
- Writes a published release for your board's crystal and CAN node number

### Before you flash an ECU

Disconnect the 12V supply and make sure the engine is off. The ECU is flashed on USB power alone.
Reconnect 12V once it is back up.

## Where the log is

If something goes wrong, the app keeps a log at `~/Library/Logs/MazduinoFlasher/flasher.log`.
**Log file** in the app opens it.

## Reporting a problem

Use **Report a problem** in the app's menu. It is sent from your Mazduino account and can attach
the log, so we can reply. You can also open an
[issue](https://github.com/mazduino/mazduino-flasher/issues) with:

- the Mazduino Flasher version (menu › About Mazduino Flasher)
- the device and the firmware you were writing
- what you did and what happened
- the log file above

## License

Mazduino Flasher is free to use. It is not open source; all rights reserved by Mazduino.

It includes open-source components, listed with their licences in the app under
**About Mazduino Flasher › Open-source notices**. Among them are these programs, used for writing firmware:

| Component | Licence | Source |
|---|---|---|
| dfu-util | GPL-2.0-or-later | https://dfu-util.sourceforge.net/ |
| esptool | GPL-2.0-or-later | https://github.com/espressif/esptool |
| avrdude | GPL-2.0-or-later | https://github.com/avrdudes/avrdude |
| libusb | LGPL-2.1-or-later | https://libusb.info/ |
| libserialport | LGPL-3.0-or-later | https://sigrok.org/wiki/Libserialport |

The Rajdhani and Chakra Petch fonts are used under the SIL Open Font License 1.1.
