#
# Copyright (C) 2015 OpenWrt.org
# Copyright (C) 2016 LEDE project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=make-ext4fs
PKG_VERSION:=2016-08-14

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://git.openwrt.org/project/make_ext4fs.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=484903e4332be6c317f531b008cb2a841a18c506
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_MIRROR_MD5SUM:=b80d6ddcd6f6925e2f5b80775bb96f3e
PKG_CAT:=zcat

HOST_BUILD_DIR:=$(COMPILE_DIR_HOST)/$(PKG_NAME)-$(PKG_VERSION)

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

ifeq ($(HOST_OS),Linux)
 MAKE_STATIC := STATIC=1
endif

define Host/Compile
	$(MAKE) -C $(HOST_BUILD_DIR) make_ext4fs $(MAKE_STATIC)
endef

define Host/Install
	$(INSTALL_BIN) $(HOST_BUILD_DIR)/make_ext4fs $(STAGING_DIR_HOST)/bin/
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/make_ext4fs
endef

$(eval $(call HostBuild))
