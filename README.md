# openwrt-imx6ull
Quick adaptation for SoMLabs VisionSOM-6ULL to OpenWrt master branch (with 4.19 kernel version)

checkout to https://github.com/openwrt/openwrt/commit/9a417fbd0d61cf01d36df0b91ed0490c06dbe5eb
Copy files to OpenWrt root dir.
Then ./scripts/feeds update -a && ./scripts/feeds install -a
Then make menuconfig, choose Target System Freescale i.MX 6 ULL, Target Profile (somlabs-sd), Target Images ext4, Boot Loaders u-boot-somlabs_visionsom_6ull.
Save and compile with make V=s -j4.
