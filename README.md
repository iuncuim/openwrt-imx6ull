# openwrt-imx6ull
Quick adaptation for SoMLabs VisionSOM-6ULL to OpenWrt master or 21.02 branch (with 5.4 kernel version)

Checkout to https://github.com/openwrt/openwrt/commit/76d90a5eaf3b7fc5bb1a1b8626db0e4e2487e876

Copy files to OpenWrt root dir.

Then ./scripts/feeds update -a && ./scripts/feeds install -a

Replace target/linux/imx6ull/dts/imx6ull_somlabs_visionsom-6ull-emmc.dts with your own (if necessary).

Then make menuconfig, choose Target System Freescale i.MX 6 ULL, Target Profile (somlabs-sd), Target Images ext4, Boot Loaders u-boot-somlabs_visionsom_6ull.

Save and compile with make V=s -j4 (or more threads to reduce compile time).
