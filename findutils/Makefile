# 
# Copyright (C) 2006-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=findutils
PKG_CPE_ID:=cpe:/a:gnu:findutils
PKG_VERSION:=4.6.0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@GNU/$(PKG_NAME)
PKG_HASH:=ded4c9f73731cd48fec3b6bdaccce896473b6d8e337e9612e16cf1431bb1169d

HOST_BUILD_PARALLEL:=1

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

$(eval $(call HostBuild))
