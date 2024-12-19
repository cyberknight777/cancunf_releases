## Build Information
```
Kernel: DragonHeart Kernel
Type: Bleeding Edge
Device: Motorola G54 5G
Compiler: LLVM 12.0.5
Branch: android12-5.10-lts
Build Number: r1a2
```
## Changelog
**-r1a2**
* Set `performance` as the default cpufreq governor to improve boot performance.

**-r1a1**
* Initial base over `android12-5.10-lts`. (commit SHA: `d4fc80b`, kver: 5.10.230)
* Compiled with LLVM 12.0.5.
* Merge `MMI-U1TD34.94-12-9-10` into the kernel.
* Backport Full LLVM support from `android13-5.10`.
* Generate a full defconfig and utilize it.
* Enable LLVM's Shadow Call Stack.
* Simplify kernel version.
* Enable `BBRv1`, `Westwood+` and `BIC` congestion algorithms.
* Fix a CFI violation in `mtk_pinconf_set()`.
* Import backlight drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import gpu drivers from `android-14-release-uhas34.29` and build them inline.
* Import fingerprint drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import touchscreen drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import connectivity drivers from `android-14-release-uhas34.29` and build them inline.
* Import met_drv_v3 driver from from `android-14-release-uhas34.29` and build them inline.
* Import sx937x and utag from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import mmi_{info,relay} drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import moto usb drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import NFC drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import power drivers from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import sm5109c driver from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Import sensors_class driver from `MMI-U1TDS34.94-12-7-6` and build them inline.
* Build `mt6855.dtb` and utilize it.
* Switch to linear brightness scaling in backlight drivers.
* Force firmware to enable single & double tap gestures in `NVT-TS`.
* Implement single and double tap detection in `NVT-TS`.
* Enable all supported gestures by default in `NVT-TS`.
* Set single tap to report `BTN_TRIGGER_HAPPY3` in `NVT-TS`.
* Enable `ILI_SET_TOUCH_STATE` to report touch states to firmware in `ILITEK_TDDI`.
* Implement single and double tap detection in `ILITEK_TDDI`.
* Enable all supported gestures by default in `ILITEK_TDDI`.
* Set single tap to report `BTN_TRIGGER_HAPPY3` in `ILITEK_TDDI`.
* Drop `focaltech_0flash_mmi_v2` driver as we don't use it at all.
* Disable MediaTek scheduler changes.
* Set `schedutil` as the default cpufreq governor.
* Implement up/down frequency transition rate limits in the `schedutil` cpufreq governor.
