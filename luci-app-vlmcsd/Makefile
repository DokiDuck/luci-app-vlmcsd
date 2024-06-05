#
# Copyright (C) 2008-2014 The LuCI Team <luci@lists.subsignal.org>
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-vlmcsd
PKG_VERSION:=1.0
PKG_RELEASE:=6

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-vlmcsd
	SECTION:=luci
	CATEGORY:=LuCI
	SUBMENU:=3. Applications
	TITLE:=LuCI support for KMS
	PKG_MAINTAINER:=<https://github.com/DokiDuck/luci-app-vlmcsd>
	PKGARCH:=all
	DEPENDS:=+vlmcsd
endef

define Package/luci-app-vlmcsd/description
	LuCI support for KMS
endef

define Build/Prepare
endef

define Build/Compile
endef

define Package/luci-app-vlmcsd/conffiles
endef

define Package/luci-app-vlmcsd/install
    $(INSTALL_DIR) $(1)/usr/lib/lua/luci
	cp -pR ./luasrc/* $(1)/usr/lib/lua/luci
	$(INSTALL_DIR) $(1)/
	cp -pR ./root/* $(1)/
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	po2lmo ./po/zh-cn/vlmcsd.po $(1)/usr/lib/lua/luci/i18n/vlmcsd.zh-cn.lmo
endef

define Package/luci-app-vlmcsd/postinst
#!/bin/sh
	rm -f /tmp/luci-indexcache
	rm -f /tmp/luci-modulecache/*
exit 0
endef

define Package/luci-app-vlmcsd/prerm
#!/bin/sh
exit 0
endef

$(eval $(call BuildPackage,luci-app-vlmcsd))
