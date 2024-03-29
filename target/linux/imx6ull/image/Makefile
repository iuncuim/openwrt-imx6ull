#
# Copyright (C) 2013-2016 OpenWrt.org
# Copyright (C) 2016 Yousong Zhou
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/image.mk

FAT32_BLOCK_SIZE=1024
SD_BOOT_PARTSIZE=40
FAT32_BLOCKS=$(shell echo $$(($(SD_BOOT_PARTSIZE)*1024*1024/$(FAT32_BLOCK_SIZE))))

KERNEL_LOADADDR:=0x85000000

define Build/sunxi-sdcard
	rm -f $@.boot
	mkfs.fat $@.boot -C $(FAT32_BLOCKS)

	mcopy -i $@.boot $(KDIR)/image-$(firstword $(DEVICE_DTS)).dtb ::dtb
	mcopy -i $@.boot $(IMAGE_KERNEL) ::uImage
	./gen_sunxi_sdcard_img.sh $@ \
		$@.boot \
		$(IMAGE_ROOTFS) \
		$(SD_BOOT_PARTSIZE) \
		$(CONFIG_TARGET_ROOTFS_PARTSIZE) \
		$(BIN_DIR)/u-boot-somlabs_visionsom_6ull/u-boot-dtb.imx
	rm -f $@.boot
endef

define Build/imx6ull-ubootimg
	rm -f $@
	rm -f $@.pad
	dd if=/dev/zero of=$@.pad bs=1024 count=1
	cat $@.pad $(BIN_DIR)/u-boot-somlabs_visionsom_6ull/u-boot-dtb.imx >$@
endef

define Build/imx6ull-mtd-full
	mv $@ $@.fw	
	$(call Build/imx6ull-ubootimg)
	dd if=/dev/zero of=$@.new bs=1M count=1
	dd if=$@ of=$@.new conv=notrunc	
	cat $@.fw >>$@.new	
	mv $@.new $@
	rm -f $@.new
endef

# why \x00\x00\x00\x00 for zImage-initramfs
define Device/Default
  PROFILES := Generic
  FILESYSTEMS := squashfs ext4
  KERNEL_INSTALL := 1
  KERNEL_SUFFIX := -uImage
  KERNEL_NAME := zImage
  KERNEL_PREFIX := $$(IMAGE_PREFIX)
  DEVICE_DTS_DIR := ../dts
endef

define Device/somlabs_spi
  DEVICE_TITLE := somlabs-spi
  DEVICE_DTS := imx6ull_somlabs_visionsom-6ull-emmc
  KERNEL := kernel-bin | append-dtb | uImage none
  IMAGE_SIZE := 15000k
  IMAGES := mtd-full.bin
  IMAGE/mtd-full.bin := append-kernel | append-rootfs | pad-rootfs | imx6ull-mtd-full
endef
TARGET_DEVICES += somlabs_spi

define Device/somlabs_sd
  DEVICE_TITLE := somlabs-sd
  DEVICE_DTS := imx6ull_somlabs_visionsom-6ull-emmc
  KERNEL := kernel-bin | uImage none
  IMAGES := sdcard.img.gz
  IMAGE/sdcard.img.gz := sunxi-sdcard | append-metadata | gzip
endef
TARGET_DEVICES += somlabs_sd

$(eval $(call BuildImage))
