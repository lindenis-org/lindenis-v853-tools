# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=lzma-old
PKG_VERSION:=4.32

PKG_SOURCE:=lzma-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://downloads.openwrt.org/sources/
PKG_MD5SUM:=5587d6ac230ad1903d504fc3253f0e42

HOST_BUILD_DIR:=$(COMPILE_DIR_HOST)/lzma-$(PKG_VERSION)

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

LIB_DIR=$(HOST_BUILD_DIR)/C/7zip/Compress/LZMA_Lib
ALONE_DIR=$(HOST_BUILD_DIR)/C/7zip/Compress/LZMA_Alone

define Host/Compile
	$(MAKE) -C $(LIB_DIR)
	$(MAKE) -f makefile.gcc -C $(ALONE_DIR)
endef

define Host/Install
	$(INSTALL_DATA) $(LIB_DIR)/liblzma.a $(STAGING_DIR_HOST)/lib/liblzma-old.a
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/lib/liblzma-old.a
endef

$(eval $(call HostBuild))
