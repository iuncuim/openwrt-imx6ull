# openwrt-imx6ull
Quick adaptation for SoMLabs VisionSOM-6ULL to OpenWrt master branch (with 4.19 and 5.4 kernel version)

Checkout to https://github.com/openwrt/openwrt/commit/46abcb3ade35adb40b91f2d5d9e05548ca625d1e

Copy files to OpenWrt root dir.

Then ./scripts/feeds update -a && ./scripts/feeds install -a

Replace target/linux/imx6ull/files/arch/arm/boot/dts/imx6ull-14x14-evk.dts with your own.

Then make menuconfig, choose Target System Freescale i.MX 6 ULL, Target Profile (somlabs-sd), Target Images ext4, Boot Loaders u-boot-somlabs_visionsom_6ull.

Save and compile with make V=s -j4.
