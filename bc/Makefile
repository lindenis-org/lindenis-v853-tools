# 
# Copyright (C) 2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=bc
PKG_VERSION:=1.06.95

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://alpha.gnu.org/gnu/bc \
	http://gnualpha.uib.no/bc/ \
	http://mirrors.fe.up.pt/pub/gnu-alpha/bc/ \
	http://www.nic.funet.fi/pub/gnu/alpha/gnu/bc/
PKG_MD5SUM:=5126a721b73f97d715bb72c13c889035

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

$(eval $(call HostBuild))
