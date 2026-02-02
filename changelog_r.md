## Build Information
```
Kernel: DragonHeart Kernel
Type: Bleeding Edge
Device: Motorola G54 5G
Compiler: LLVM 12.0.5
Branch: android12-5.10
Build Number: r2b2
```
## Changelog
**-r2b2**
* Backport TEO (Timer-Events Oriented) cpuidle governor from mainline. (as of 6.19.0-rc8)
* Prioritize TEO over other cpuidle governors.

**-r2b1**
* Backport fuse-bpf from android13-5.15 to reduce overhead with FUSE lookups.

**-r2a3**
* Implement CLOSE_RANGE_CLOEXEC flag on close_range() from android13-5.10 to fix an issue where hotspot and tethering doesn't work on Android 16 QPR2.
* Implement epoll_pwait2() syscall from android13-5.15 to fix a massive logspam on Android 16 QPR2.

**-r2a2**
* Drop NL80211_WPA_VERSION_3 enumeration on wlan driver.
* Call wlanRemove() after wlanOnAtReset() fails.
* Add WPA3 support in security types on wlan driver.
* Support WAPI-SMS4 block cipher when WAPI is supported.
* Implement fixes for Wi-Fi roaming and miscellanous issues from bogota (Moto G56).
* Enable Wi-Fi channel 144 for Japan.
* Implement CVE fixes for GPU from bogota (Moto G56).
* Implement memory leak fixes for GPU from bogota (Moto G56).

**-r2a1**
* Initial base over android12-5.10. (commit SHA: 070f0e34d716, kver: 5.10.240)
* Compiled with LLVM 12.0.5.
* Merge MMI-V1TDS35H.83-20-5-5 into the kernel.
* Backport Full LLVM support from android13-5.10.
* Generate a full defconfig and utilize it.
* Enable LLVM's Shadow Call Stack.
* Simplify kernel version.
* Enable BBRv1, Westwood+ and BIC congestion algorithms.
* Fix CFI violations in mtk_pinconf_set() and mtk_pinconf_get().
* Import backlight drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import gpu drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import fingerprint drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import touchscreen drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import connectivity drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import sx937x and utag from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import mmi_{info,relay} drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import NFC drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import power drivers from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import sm5109c driver from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Import sensors_class driver from MMI-V1TDS35H.83-20-5-5 and build them inline.
* Drop met_drv_v3 and Moto USB drivers.
* Build mt6855.dtb and utilize it.
* Switch to linear brightness scaling in backlight drivers.
* Force firmware to enable single & double tap gestures in NVT-TS.
* Implement single and double tap detection in NVT-TS.
* Enable all supported gestures by default in NVT-TS.
* Set single tap to report BTN_TRIGGER_HAPPY3 in NVT-TS.
* Enable ILI_SET_TOUCH_STATE to report touch states to firmware in ILITEK_TDDI.
* Implement single and double tap detection in ILITEK_TDDI.
* Enable all supported gestures by default in ILITEK_TDDI.
* Set single tap to report BTN_TRIGGER_HAPPY3 in ILITEK_TDDI.
* Drop focaltech_0flash_mmi_v2 driver as we don't use it at all.
* Disable MediaTek scheduler changes.
* Set schedutil as the default cpufreq governor.
* Implement up/down frequency transition rate limits in the schedutil cpufreq governor.
* Set performance as the default cpufreq governor to improve boot performance.
* Add NL80211_WPA_VERSION_3 enumeration to wlan driver to fix WPA3-SAE on A15 QPR1+ (modules).
* Backport Sony HID drivers from mainline.
* Implement UVC (DeviceAsWebcam) support in USB drivers.
* Switch to host cpio and tar binaries as utilising prebuilt binaries shipped by MTK BSP is redundant.
* Fix random Wi-Fi disconnection issues in connectivity drivers.
* Disable more MTK Scheduler drivers.
* Load NVT-TS firmware earlier.
* kramel: Implement _depmod() to generate AOSP-compatible vendor_ramdisk fragment and vendor_dlkm modules.
* kramel: Standardize and clean-up most of the code.
* Implement fs_config and file_contexts generation in _depmod().
* Set CONFIG_NR_CPUS to 8 as we are on a 8-core CPU device.
* Disable AEE and Hang Detect Monitor as they are useless debugging drivers.
* Stop building MediaTek DCM drivers for other platforms.
* Drop DVFSRC Helper for MET.
* Disable MediaTek's ATF Logger.
* Drop met_drv_v3 modules from vendor_dlkm list.
* Fix building with AEE disabled.
* Import LZ4 v1.10.0 from upstream.
* Import arm64 V8 ASM lz4 decompression algorithm.
* Update assembly instructions of lz4armv8 from Huawei kernel drop.
* Use ARM64 v8 ASM to accelrate lz4 decompression in crypto, IncFS and EROFS.
* Update drivers from MMI-V1TDC35H.44-20-15.
* Backport support to make $(LLVM) more flexible.
* Build Image.gz and mediatek/mt6855.dtb targets by default.
* Implement high brightness mode (HBM) support.
* Implement content aware brightness control (CABC) support.
* kramel: Copy LZ4-compressed CPIO archive to prebuilt kernel tree.
* Disable redundant flashlight drivers.
* Copy max torch duty to userspace.
* Implement a FLASH_IOC_GET_CURRENT_TORCH_DUTY ioctl.
* kramel: Allow updating modules.load.recovery in platform(default) vendor_ramdisk fragment.
* Disable MTK RPS (Receive-Packet Steering) because we don't need MTK's network load balancer as the scheduler can handle the load balancing on its own.
* Disable MTK RPS in gen4m.
* Let scheduler handle cpu boosting in gen4m.
* Disable CPU boosting from wlan by default.
* Disable unneeded debug cruft such as KASAN, KFENCE, CFI, SCS, UBSAN, PAGE_EXTENSION, PAGE_OWNER, PAGE_PINNER, DEBUG_MEMORY_INIT as GKIs are tested against these debuggers as such we do not need to keep them enabled on production builds.
* Enable TTL/HL fixation as some carriers offer lower data exclusively for tethering so allow bypassing it.
* Reduce an abundance of logspam treewide.
* Disable connectivity wakelocks.
* Queue delayed work on power efficient workqueues for connectivity.
* Disable all build-time spams.
* Disable IKHEADERS as it increases the kernel Image size by approximately 4MB.
* Silence warnings generated by DTC.
* Don't allow userspace to write to /dev/kmsg to silence userspace logging in dmesg.
* Use the stock GKI config for /proc/config.gz to pass VINTF checks.
* Disable MET tracing support in gen4m.
* Bump 2.4GHz hotspot bandwidth to 40MHz for improved stability and throughput.

**-r1b3**
* Merge `MMI-U1TDS34.94-12-9-10-2` into the kernel.
* Update connectivity drivers to `MMI-U1TDS34.94-12-9-10-2` a.k.a Android 14 January SPL (modules).
* Update gpu drivers to `MMI-U1TDS34.94-12-9-10-2` a.k.a Android 14 January SPL (modules).
* Switch to host cpio and tar binaries as utilising prebuilt binaries shipped by MTK BSP is redundant.

**-r1b2**
* Implement UVC (DeviceAsWebcam) support in USB drivers.

**-r1b1**
* AK3: Uncomment vendor_boot install methods.
* AK3: Use appropriate APIs for vendor_boot install to retain recovery ramdisk.
* AK3: Update magiskboot to fix generation of garbage boot images.

**-r1a3**
* Add NL80211_WPA_VERSION_3 enumeration to wlan driver to fix WPA3-SAE on A15 QPR1+ (modules).
* Backport Sony HID drivers from mainline.

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
