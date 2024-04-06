# Liteburner

Ender 3 V3 KE Dual 5015 Blower Fan Shroud

<img src="https://github.com/iamlite/liteburner/blob/main/Images/Img_2.jpeg" alt="Liteburner" width="500">

This repository is meant to be used as a central location to keep important files and information about the liteburner.

The main challenge right now is having the LED ring play certain animations for different printer states.

## Ideas & Progress

- [x] Set up presets in WLED for different statuses.
- [x] Trigger those presets with gcode macros.
- [x] Preset animation when the printer is heating up.
- [x] Preset animation when the printer is done printing.
- [ ] Preset animation when the printer is cooling down.
- [ ] Preset animation when the printer is paused.
- [ ] Preset animation when the printer is resuming.
- [ ] Preset animation when the printer is stopping.
- [x] ⭐️ Print progress displayed on the ring. 1 LED turns on for every 12.5% of print progress while playing a preset animation.

## To set up your LED Ring

*Disclaimer: your wled instance should be named "KELED", otherwise you will need to go through and edit the name for your own.*

1. Go to your WLED url > config > Security & Updates > Backup & Restore
2. Upload the [json file](https://github.com/iamlite/liteburner/blob/main/wled_presets_KELED.json) there and restart the WLED.
3. Go to your klipper UI of choice find your configuration files and open moonraker.conf. Copy [this](https://github.com/iamlite/liteburner/blob/main/moonraker.conf) into there.
4. The next step is the [Gcode Macro]. I've included a copy of my gcode_macro file in this repo. Please note it has some extras such as nozzle cleaning and my own custom start script. Feel free to use it, but do so at your own risk.

The follow macros should be copied into your gcode_macro.cfg file from the gcode_macro file in this repo. Please edit the START_PRINT and END_PRINT macros to your needs.

   - START_PRINT
   - END_PRINT
   - UPDATE_WLED_PROGRESS

5. Open your slicer and add the following to your machine Gcode.

**Machine Start G-code:**

`START_PRINT BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer]`

**Machine End G-code:**

`END_PRINT`

**Layer Change G-code:**

`UPDATE_WLED_PROGRESS`

## Bill of Materials (BOM)

- 2x M3 L4 Flat Head Screws
- 2x M3 L10 Screws
- 4x M3 L20 Screws
- 2x 5015 24V Blowers

### Optional

-   1x 24V LED
-   1x 8Bit WS2812 LED Ring

## Links

- [24V LED on Aliexpress](<https://s.click.aliexpress.com/e/_Dky6Lzx>)
- [LED Ring on Aliexpress](<https://s.click.aliexpress.com/e/_DD0RQdB>)
- [24V 5015 Blower on Aliexpress](<https://s.click.aliexpress.com/e/_DBk6D53>)

## Print Settings

- Material: Ideally use something other than PLA; I used PETG.
- Supports: None required. If using Orca slicer, the auto-orient feature does all the work for you.
- Walls: Use at least 3 walls.
