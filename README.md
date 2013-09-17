Motorola XT910 2 Slimbean
=========================

Port the Motorola XT 910 (codename: umts_spyder) to Slimbean Source.

The platform_manifest repository mainly came from Slimbbean source but some files had to correct/modify to build Slimbean source to Motorola XT 910 (umts_spyder).

The following files had to add:

 (CyanogenMod) android_device_motorola_umts_spyder/slim.dependencies (destination="device/motorola/umts_spyder/slim.dependencies")
 (CyanogenMod) android_device_motorola_umts_spyder/slim.mk (destination="device/motorola/umts_spyder/slim.mk")
 (CyanogenMod) android_device_motorola_umts_spyder/vendorsetup.sh (destination="device/motorola/umts_spyder/vendorsetup.sh")

The following files had to modify:   

 (SlimROMs) android_hardware_ti_wlan /mac80211/wpa_supplicant_lib/Android.mk (destination="hardware/ti/wlan/mac80211/wpa_supplicant_lib/Android.mk)
 (SlimROMs) android_hardware_ti_wpan /bluedroid_wilink/Android.mk (destination="hardware/ti/wpan/bluedroid_wilink/Android.mk)
 (CyanogenMod) kernel_motorola_omap4-common /BoardConfigCommon.mk (destination="kernel/motorola/omap4-common/BoardConfigCommon.mk)
 (SlimROMs) vendor_slim /tools/squisher (destination="vendor/slim/tools/squisher)

How to build ROM:

mkdir 'working directory'
cd 'working directory'
repo init -u https://github.com/szirog/platform_manifest.git -b master
repo sync
. build/envsetup.sh
lunch
(choose slim_umts_spyder)
make -j8 bacon

2013.09.17


