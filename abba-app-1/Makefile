#	
# PACKAGE HELLO WORLD
#

include $(TOPDIR)/rules.mk

# Name, version and release number
# The name and version of your package are used to define the variable to point to the build directory of your package: $(PKG_BUILD_DIR)
PKG_NAME:=abba-app-1
PKG_SOURCE_DATE:=2020-05-07
PKG_VERSION:=2020-05-07
#PKG_RELEASE:=1

PKG_LICENSE:=MIT

#
#PKG_BUILD_DIR=$(BUILD_DIR)/$(PKG_NAME)-$(BUILD_VARIANT)
#
# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
# SOURCE_DIR:=files
#

include $(INCLUDE_DIR)/package.mk

# Package definition; instructs on how and where our package will appear in the overall configuration menu ('make menuconfig')
define Package/abba-app-1
  SUBMENU:=ABBA
  SECTION:=myopenwrtpackages
  CATEGORY:=Extra packages
  TITLE:=Test appliacation for OpenWRT
endef

# Package description; a more verbose description on what our package does
define Package/abba-app-1/description
A testing application.
endef

# Source settings (i.e. where to find the source codes)
# This is a custom variable, used below
#USE_SOURCE_DIR:=files

# Package preparation instructions; create the build directory and copy the source code. 
# The last command is necessary to ensure our preparation instructions remain compatible with the patching system.
define Build/Prepare
	@echo '...'
	@echo 'Prepare $(PKG_NAME) to $(PKG_BUILD_DIR) ...'
	$(Build/Prepare/Default)
#	mkdir -p $(PKG_BUILD_DIR)
#	$(CP) ./src/* $(PKG_BUILD_DIR)
endef

define Build/Configure
	@echo '...'
	@echo 'Configure $(PKG_NAME) ...'
endef

# Package build instructions; invoke the target-specific compiler to first compile the source file, and then to link the file into the final executable
define Build/Compile
	@echo 'Compile $(PKG_NAME) to $(PKG_BUILD_DIR) ...'
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS)" \
		LDFLAGS="$(TARGET_LDFLAGS)"
#	$(MAKE) $(KERNEL_MAKEOPTS) SUBDIRS="$(PKG_BUILD_DIR)" modules
endef

# Package install instructions; create a directory inside the package to hold our executable, and then copy the executable we built previously into the folder
define Package/abba-app-1/install
	@echo 'Install $(PKG_NAME) to $(PKG_BUILD_DIR) ...'
#	$(Build/Install/Default)
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/bin
endef

#define Build/Install
#	@echo 'Install $(PKG_NAME) to $(PKG_BUILD_DIR) ...'
#	$(Build/Install/Default)
#endef

# This command is always the last, it uses the definitions and variables we give above in order to get the job done
$(eval $(call BuildPackage,abba-app-1))
