# 
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=patchelf
PKG_VERSION:=0.8

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://nixos.org/releases/patchelf/patchelf-$(PKG_VERSION)
PKG_MD5SUM:=5b151e3c83b31f5931b4a9fc01635bfd

HOST_BUILD_PARALLEL:=1
HOST_FIXUP:=autoreconf

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

define Host/Install
	$(INSTALL_DIR) $(STAGING_DIR_HOST)/bin
	$(INSTALL_BIN) $(HOST_BUILD_DIR)/src/patchelf $(STAGING_DIR_HOST)/bin/patchelf
endef

$(eval $(call HostBuild))
