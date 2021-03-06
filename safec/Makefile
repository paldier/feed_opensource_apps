# 
# Copyright (C) 2012, 2013 Cisco Systems
#
# This Makefile for Safe c library
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libsafec
PKG_VERSION:=v10052013
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/rurban/safeclib.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=v10052013
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_MAINTAINER:=Bo Berry <bberryusa@users.sourceforge.net>
PKG_MIRROR_HASH:=aa14466f7f6d6cb1518e5334cbd72d132ca5a8cec71f396457560e7fd939d662

PKG_LICENSE:=CISCO SYSTEMS
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_FIXUP:=autoreconf

PKG_INSTALL:=1


include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/target.mk

define Package/safeclibs/default
  TITLE:=Safec library build
  SECTION:=libs
  CATEGORY:=Libraries
  PROVIDES:=libsafec
  URL:=https://github.com/rurban/safeclib.git
  VERSION:=v10052013
endef

define Package/safeclibs
  $(call Package/safeclibs/default)
  TITLE+= (default safec library)
endef

define Package/safeclibs/description
 This package contains the safec  shared library.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libsafec/* $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsafec-1.0.{a,so*} $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/safec-1.0.pc $(1)/usr/lib/pkgconfig/
endef

define Package/safeclibs/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsafec-1.0.so* $(1)/usr/lib/
endef


$(eval $(call BuildPackage,safeclibs))
