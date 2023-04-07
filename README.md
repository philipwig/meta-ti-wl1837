# meta-ti-wl1837
Yocto layer with required firmware and programs for wilink 8 drivers to support wl1837 module

You will also need to include wpa_supplicant, hostapd, and iw but these recipes are part of base yocto openembedded layers.
Also need wireless-regdb somehow, for Petalinux and zynq 7000 I used wireless-regdb-static

## Kernel Configuration 
Below is the kernel configuration for the wireless drivers. Seems to work but I don't know if it is complete
```
CONFIG_WLAN=y

CONFIG_WIRELESS=y
CONFIG_CFG80211=m
CONFIG_NL80211_TESTMODE=y

CONFIG_MAC80211=m
CONFIG_MAC80211_LEDS=y

CONFIG_WL_TI=y
# CONFIG_WL1251 is not set
CONFIG_WL12XX=m
CONFIG_WL18XX=m
CONFIG_WLCORE=m
CONFIG_WLCORE_SDIO=m
CONFIG_WILINK_PLATFORM_DATA=y

CONFIG_KEYS=y
CONFIG_SECURITY=y
CONFIG_CRYPTO=y
CONFIG_MAC80211_MESH=y
CONFIG_DEBUG_FS=y
CONFIG_MAC80211_DEBUGFS=y
CONFIG_NL80211_TESTMODE=y
CONFIG_CRYPTO_USER_API=y
CONFIG_CRYPTO_USER_API_ENABLE_OBSOLETE=y
CONFIG_CRYPTO_ARC4=y
CONFIG_CRYPTO_ECB=y
CONFIG_CRYPTO_AES=y
CONFIG_CRYPTO_MICHAEL_MIC=y
CONFIG_CRYPTO_CCM=y
CONFIG_CRYPTO_GCM=y
CONFIG_RFKILL=y
CONFIG_REGULATOR_FIXED_VOLTAGE=y
CONFIG_CRC7=y
CONFIG_INPUT_MISC=y
CONFIG_INPUT_UINPUT=y

CONFIG_ARM_CRYPTO=y
CONFIG_CRYPTO_SHA1_ARM=y
CONFIG_CRYPTO_SHA256_ARM=y
CONFIG_CRYPTO_SHA512_ARM=y
# CONFIG_CRYPTO_BLAKE2S_ARM is not set
CONFIG_CRYPTO_AES_ARM=y
# CONFIG_CRYPTO_CHACHA20_NEON is not set
# CONFIG_CRYPTO_POLY1305_ARM is not set
```
