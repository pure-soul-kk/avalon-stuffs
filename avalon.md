## Instructions for Oneplus Nord 4

> [!CAUTION]
> - Your warranty is void. Or valid, probably?
> - I am not responsible for any damage you made to your device. You have been warned!
> - Don't fall for mod/cracks etc and you may end up in trouble, in such scenarios you are not to blame us.

> [!Warning]
> * I are not responsible for anything that may happen to your phone by installing custom ROMs.
> * I are not responsible for anything that may happen to your phone by installing any kernels.
> * You do it at your own risk and take the responsibility upon yourself
> * You are not to blame respected developers for any of your loss.
> * Be careful while going through download, installation guide

> [!Tip]
> **Basic Notes for all users:**  
> * These will only work if you follow every section and step precisely
> * Do not continue after something fails! Contact the developer or ask in the support group for help!
> * The device must have an unlocked bootloader & has Platform Tools installed in pc.
> * Make backup of your important data and file

### Prerequisites:
- Device must be running OxygenOS version 15.0.0.702 or higher,
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
- Sideload ROM zip
```
adb sideload PixelOS*.zip
```
- Format data after sideload
- Reboot and voila!

>[!NOTE]
> **If sideloading rom gives error 7:**
>
> Reboot to fastbootd (enter fastboot option on recovery) and wipe the super partition using:
```
fastboot wipe-super super_empty.img
```
- Enter recovery
- Sideload the rom zip
- Format data
- Reboot

### Updating to a newer build (dirty flash):
- Sideload ROM zip
- Reboot and voila!

### If after sideloading rom, device boots to bootloader:
- Do clean flash steps again
- When it asks for Yes/No prompt for installing additional packages, select Yes
- After device reboots recovery, sideload again.
- This time when it asks for Yes/No prompt for installing additional packages, select No
- Format and Reboot
