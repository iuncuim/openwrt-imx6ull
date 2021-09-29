include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_VERSION:=2020.10
PKG_HASH:=0d481bbdc05c0ee74908ec2f56a6daa53166cc6a78a0e4fac2ac5d025770a622

include $(INCLUDE_DIR)/u-boot.mk
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk

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
  NAME:=SoMLabs VisionSOM-6ULL board
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
