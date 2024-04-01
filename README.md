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
- [ ] ⭐️ Print progress displayed on the ring. 1 LED turns on for every 12.5% of print progress while playing a preset animation.

*This has been achieved and works really well, through home assistant. Both WLED and Moonraker have integration with Home Assistant. The Moonraker integration in HA exposes print progress so making an automation to trigger based on progress is very simple.*

**THE ISSUE:** While using Home Assistant is an easy option, it should not be necessary. Ideally we have Moonraker and WLED communicate with eachother for print progress, just as they do for other things via macros. This is still a WIP.

YAML for home assistant automation can be found above.

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
