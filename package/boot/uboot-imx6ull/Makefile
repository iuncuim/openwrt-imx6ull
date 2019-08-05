include $(TOPDIR)/rules.mk

PKG_NAME:=uboot-imx6ull
PKG_SOURCE_DATE:=2018-09
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/SoMLabs/somlabs-uboot-imx.git
PKG_SOURCE_VERSION:=dbe68c464c301ddcd83ca4c09d7bf93baf85ed5e

include $(INCLUDE_DIR)/u-boot.mk
include $(INCLUDE_DIR)/package.mk

define U-Boot/Default
  BUILD_TARGET:=imx6ull
  UBOOT_IMAGE:=u-boot-dtb.imx
endef

define U-Boot/mx6qsabresd
  NAME:=SABRE i.MX6Quad board
endef

define U-Boot/nitrogen6dl
  NAME:=Nitrogen6x i.MX6Dual-Lite 1GB board
endef

define U-Boot/nitrogen6dl2g
  NAME:=Nitrogen6x i.MX6Dual-Lite 2GB board
endef

define U-Boot/nitrogen6q
  NAME:=Nitrogen6x/SABRE Lite (MX6Q/1GB)
endef

define U-Boot/nitrogen6q2g
  NAME:=Nitrogen6x i.MX6Quad 2GB board
endef

define U-Boot/nitrogen6s
  NAME:=Nitrogen6x i.MX6Solo 512MB board
endef

define U-Boot/nitrogen6s1g
  NAME:=Nitrogen6x i.MX6Solo 1GB board
endef

define U-Boot/wandboard_dl
  NAME:=Wandboard Dual Lite
  BUILD_DEVICES:=wandboard
endef

define U-Boot/wandboard_quad
  NAME:=Wandboard Quad
  BUILD_DEVICES:=wandboard
endef

define U-Boot/wandboard_solo
  NAME:=Wandboard Solo
  BUILD_DEVICES:=wandboard
endef

define U-Boot/somlabs_visionsom_6ull
  NAME:=NXP ls1012afrdm 64b Dev Board
endef

UBOOT_TARGETS := \
  mx6qsabresd \
  nitrogen6dl \
  nitrogen6dl2g \
  nitrogen6q \
  nitrogen6q2g \
  nitrogen6s \
  nitrogen6s1g \
  wandboard_dl \
  wandboard_quad \
  wandboard_solo \
  somlabs_visionsom_6ull

$(eval $(call BuildPackage/U-Boot))
