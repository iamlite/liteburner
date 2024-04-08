# Liteburner

Ender 3 V3 KE Dual 5015 Blower Fan Shroud

<img src="https://github.com/iamlite/liteburner/blob/main/Images/Img_2.jpeg" alt="Liteburner" width="500">

This repository is meant to be used as a central location to keep important files and information about the liteburner.

This is a work in progress. Im still learning and trying to figure out how best to do things. I'm updating and tweaking frequently so make sure to check back often.

## Ideas & Progress

- [x] Set up presets in WLED for different statuses.
- [x] Trigger those presets with gcode macros.
- [x] ⭐️ Print progress displayed on the ring. 1 LED turns on for every 12.5% of print progress while playing a preset animation.

## To set up your LED Ring

*Disclaimer: your wled instance should be named "KELED", otherwise you will need to go through all these files and edit the name for your own.*

1. Go to your WLED web ui > Config > Security & Updates > Backup & Restore. Upload [this json file](https://github.com/iamlite/liteburner/blob/main/wled_presets_KELED.json) there and reboot WLED.

2. Go to your klipper UI of choice, find your configuration files and open moonraker.conf. Copy [this](https://github.com/iamlite/liteburner/blob/main/moonraker.conf) into there. Edit the IP address to your own WLED IP.

3. Go to printer.cfg and add `[include wled_macro.cfg]` somewhere with your other includes at the top of your file. Then add [the wled_macro.cfg file](https://github.com/iamlite/liteburner/blob/main/wled_macro.cfg) to your config folder.

4. I've included a copy of my gcode_macro file in this repo. It is the stock gcode_macro.cfg file for the KE. I've added start and stop macros and inserted some WLED stuff into the the various other macros. > [gcode_macro.cfg](https://github.com/iamlite/liteburner/blob/main/gcode_macro.cfg)

    - You can replace your file with my gcode_macro.cfg or edit as needed if you have your own stuff to add to it :)

5. Open your slicer and add the following to your machine Gcode.

    **Machine Start G-code:**

    `START_PRINT BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer]`

    **Machine End G-code:**

    `END_PRINT`

    **Layer Change G-code:**

    `UPDATE_WLED_PROGRESS`

Done! Now you can start printing and your LED ring should automatically turn on and switch presets as it prints. 

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
