# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=lzma
PKG_VERSION:=4.65

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://downloads.openwrt.org/sources/
PKG_MD5SUM:=434e51a018b4c8ef377bf81520a53af0

HOST_BUILD_DIR:=$(COMPILE_DIR_HOST)/$(PKG_NAME)-$(PKG_VERSION)

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

UTIL_DIR=$(HOST_BUILD_DIR)/C/LzmaUtil
ALONE_DIR=$(HOST_BUILD_DIR)/CPP/7zip/Compress/LZMA_Alone

define Host/Compile
	$(MAKE) -C $(UTIL_DIR) -f makefile.gcc
	$(MAKE) -C $(ALONE_DIR) -f makefile.gcc
endef

define Host/Install
	$(INSTALL_DIR) $(STAGING_DIR_HOST)/bin
	$(INSTALL_BIN) $(HOST_BUILD_DIR)/CPP/7zip/Compress/LZMA_Alone/lzma_alone $(STAGING_DIR_HOST)/bin/lzma
endef

define Host/Clean
endef

$(eval $(call HostBuild))
