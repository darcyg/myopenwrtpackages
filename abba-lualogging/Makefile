#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=abba-lua-logging
PKG_VERSION:=2019
PKG_RELEASE:=1

#PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
#PKG_SOURCE_URL:=https://codeload.github.com/keplerproject/wsapi/tar.gz/v$(PKG_VERSION)?
#PKG_HASH:=48dc7aba0fd2e96a3e5ef51045b5d923964f6ae299de761aa0467031ad44e987

PKG_SOURCE_URL:=https://github.com/vartamonov/fork-lualogging.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=master

### PKG_BUILD_DIR:=$(BUILD_DIR)/wsapi-$(PKG_VERSION)
#PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
### PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(BUILD_VARIANT)/$(PKG_NAME)-$(PKG_VERSION)

#PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/abba-lua-logging
    SUBMENU:=ABBA
    SECTION:=myopenwrtpackages
    CATEGORY:=Extra packages
    TITLE:=LUA logging
    DEPENDS:=+luasocket
endef

define Package/abba-lua-logging/description
	LuaLogging provides a simple API to use logging features in Lua.
	Its design was based on log4j. LuaLogging currently supports,
	through the use of appenders, console, file, rolling file, email, socket and sql outputs.
endef

define Build/Configure
	@echo 'Configure $(PKG_NAME) ...'
	@$(call MESSAGE, "TEST ...")
	@pwd
	@ls
endef

define Build/Compile
	@echo 'Compile $(PKG_NAME) ...'
endef

define Build/Install
	@echo 'Install $(PKG_NAME) ...'
	@pwd
	@ls
endef

define Package/abba-lua-logging/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/logging.lua $(1)/usr/lib/lua

##	$(INSTALL_DIR) $(1)/usr/bin
##	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/launchers/* $(1)/usr/bin

	$(INSTALL_DIR) $(1)/usr/lib/lua/logging
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/logging/*.lua $(1)/usr/lib/lua/logging

endef

$(eval $(call BuildPackage,abba-lua-logging))
