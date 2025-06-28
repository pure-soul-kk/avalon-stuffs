## Instructions for Oneplus Nord 4

### Prerequisites:
- Device must be running OxygenOS version 15.0.0.720 or higher,
- Flash the current build again using local install to ensure both slots have the same firmware. (Failing to do so will get you bricked)
- Unlocked Bootloader [Guide](https://wiki.lineageos.org/devices/salami/install/#unlocking-the-bootloader)
  
### Clean flash:
- Reboot to bootloader
```
adb reboot bootloader
```
- Flash boot, init_boot, vendor_boot, dtbo and recovery images
```
fastboot flash boot boot.img
```
```
fastboot flash init_boot init_boot.img
```
```
fastboot flash vendor_boot vendor_boot.img
```
```
fastboot flash dtbo dtbo.img
```
```
fastboot flash recovery recovery.img
```

- Wipe Data
```
fastboot -w
```

- Reboot to recovery
```
fastboot reboot recovery
```
- While in recovery mode, factory reset (wipe/format data).
- Reboot to fastbootd (enter fastboot option on recovery) and wipe the super partition using "fastboot wipe-super super_empty.img"
- Now reboot back to recovery
```
fastboot reboot recovery
```
- Sideload ROM zip
```
adb sideload PixelOS*.zip
```
- Format data after sideload
- Reboot and voila!

### Updating to a newer build (dirty flash):
- Sideload ROM zip
- Reboot and voila!

### If after sideloading rom, device boots to bootloader:
- Do clean flash steps again
- When it asks for Yes/No prompt for installing additional packages, select Yes
- After device reboots recovery, sideload again.
- This time when it asks for Yes/No prompt for installing additional packages, select No
- Format and Reboot
