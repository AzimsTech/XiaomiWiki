## Anti-Rollback Protection explained

Anti-Rollback Protection (ARP) was introduced by Google in Android 8.0 Oreo and they made its implementation mandatory for devices launching with Android 9.0 Pie. ARP is a security countermeasure aiming to prevent devices from booting older, less-secure versions of Android. In Google's implementation, ARP is disabled if the bootloader is unlocked, whereas on Xiaomi devices it cannot be disabled once it's enabled by a ROM that implements it. Xiaomi likely made this decision to stop resellers from exploiting vulnerabilities found in older versions of MIUI.

### Checking if ARP is enabled

1. Download and launch the Xiaomi ADB/Fastboot Tools from [here](tools.md).

2. Connect the device to your computer and load it in Fastboot mode. The device info should appear in the application.

    For details, see the instructions on GitHub.

If don't get any number for anti version, ARP isn't enabled. If you get a number, ARP is enabled.

### Anti version explained

Having an anti version means that you cannot flash whatever ROM you want, only ROMs that have an anti version equal to or higher than the device's.

* Flashing a ROM with an anti version higher than the device's will set it to the higher value.
* Flashing a ROM with an anti version equal to the device's won't change anything.
* Flashing a ROM with an anti version lower than the device's will result in a hard brick.

For now, only Fastboot ROMs check for anti version and act accordingly. They will abort without making any changes if the device's anti version is higher than its own.

Custom ROMs are unaffected by ARB and flashing them won't brick the device or change the anti version.

### ARP-enabled devices

* Mi 6X (wayne)
* Mi 8 (dipper)
* Mi Max 3 (nitrogen)
* Redmi 6 Pro (sakura)
* Redmi Note 5 (whyred)