#
# Copyright (C) 2009-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=upslug2
PKG_VERSION:=20071227

PKG_SOURCE_URL:=http://svn.nslu2-linux.org/svnroot/upslug2/trunk
PKG_SOURCE_PROTO:=svn
PKG_SOURCE_SUBDIR:=upslug2-$(PKG_VERSION)
PKG_SOURCE_VERSION:=41
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2

HOST_PREBUILT:=1

include $(BUILD_DIR)/host-build.mk

unexport CFLAGS

define Host/Configure
	(cd $(HOST_BUILD_DIR); \
		aclocal && autoconf && \
		autoheader && \
		automake --add-missing; \
	)
	$(Host/Configure/Default)
endef

ifneq ($(HOST_OS),Linux)
	HOST_CONFIGURE_ARGS += --with-libpcap
endif

$(eval $(call HostBuild))
