#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=mkimage
PKG_VERSION:=2018.03

PKG_SOURCE:=u-boot-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://ftp.denx.de/pub/u-boot
PKG_HASH:=b50d8b6fe0d90b92c8c147457b1b4c2ed1cdb03191085cfc57fdad77c0bfffab

HOST_BUILD_DIR:=$(COMPILE_DIR_HOST)/u-boot-$(PKG_VERSION)

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

HOSTLDFLAGS += -static

define Host/Prepare
	$(Host/Prepare/Default)
	mkdir -p $(HOST_BUILD_DIR)/include/config
	touch $(HOST_BUILD_DIR)/include/config/auto.conf
endef

define Host/Compile
	$(MAKE) -C $(HOST_BUILD_DIR) \
		HOSTCFLAGS="$(HOST_CFLAGS)" \
		HOSTLDFLAGS="$(HOST_LDFLAGS)" \
		no-dot-config-targets=tools-only \
		CONFIG_MKIMAGE_DTC_PATH=dtc \
		CONFIG_FIT_SIGNATURE=y \
		tools-only
endef

define Host/Install
	$(CP) $(HOST_BUILD_DIR)/tools/mkimage $(STAGING_DIR_HOST)/bin/
	$(CP) $(HOST_BUILD_DIR)/tools/mkenvimage $(STAGING_DIR_HOST)/bin/
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/mkimage
	rm -f $(STAGING_DIR_HOST)/bin/mkenvimage
endef

$(eval $(call HostBuild))
