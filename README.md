# INFINIX MOBILITY LIMITED™

### repositories ###

###### TWRP available
* https://github.com/search?q=X657B&type=repositories

###### LICENSE
https://github.com/LinggaCR17/BasedSources-X657B/blob/main/LICENSE

### OFFICIAL STOCK RELEASE ###
https://www.needrom.com/download/infinix-x657b/

Firmware (fw) details:
BasedA10, BasedA11, ARM32-binder with ARM64-bit SoC.

### A10 vndk 29.0 & A11 vndk 30.0 ###
* Installing GSI's Requirements

![1000009250](https://github.com/LinggaCR17/BasedSources-X657B/assets/43074091/c253448d-ad8a-48d1-9133-42e6b19f8a3d)

### For example ###
* system-arm32_binder64-ab.img.xz

![1000009251](https://github.com/LinggaCR17/BasedSources-X657B/assets/43074091/786c6f62-8bb0-422c-85de-364b93eb0a87)

### Additional

* requirements stock (fw)
###### vbmeta.img, vbmeta_system.img, vbmeta_vendor.img, boot.img, recovery.img

![1000009257](https://github.com/LinggaCR17/BasedSources-X657B/assets/43074091/84360dc8-2579-4e18-8834-eaa88a069c0f)


	on screen
		adb devices -> (allow)
		adb reboot bootloader
		
	on bootloader
		fastboot devices
		fastboot --disable-verification flash vbmeta vbmeta.img
		fastboot --disable-verification flash vbmeta vbmeta_system.img
		fastboot --disable-verification flash vbmeta vbmeta_vendor.img
		
	on bootloader (options)
		fastboot flash boot magisk_patch-boot.img
		fastboot flash recovery your_twrp-recovery.img
		
	fastboot reboot fastboot
	
	on fastbootd
		fastboot getvar is-userspace
		fastboot delete-logical-partition system_ext
		fastboot delete-logical-partition product
		
###### system-arm32_binder64-ab.img.xz -> extract system-arm32_binder64-ab.img
###### rename system-arm32_binder64-ab.img -> system.img

	on fastbootd (installing)
		fastboot erase system
		fastboot flash system system.img
		
	on fastbootd (options)
		fastboot -w <- (wipe)
		
		fastboot reboot
		
		or:
		
		fastboot reboot recovery
		
