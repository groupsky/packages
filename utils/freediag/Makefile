include $(TOPDIR)/rules.mk

PKG_NAME:=freediag
PKG_VERSION:=1.05
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-src
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-src.tar.gz
PKG_SOURCE_URL:=@SF/freediag
PKG_MD5SUM:=ce26abcd616803b63c782e00e55da100
PKG_CAT:=zcat
PKG_MAINTAINER=Geno Roupsky <groupsky@gmail.com>

PKG_LICENSE:=GPL-2.0+
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/freediag
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Vehicle Diagnostics Suite
  URL:=http://freediag.sourceforge.net/
	DEPENDS:=+librt
endef

define Package/freediag/description
 Mostly OBDII-compliant scantool and diagnostic software
 Vehicle diagnostic program including OBDII Scantool and support for
 certain manufacturer-specific controllers.
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	chmod a+x $(PKG_BUILD_DIR)/configure
endef

define Package/freediag/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/scantool/scantool $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/scantool/diag_test $(1)/usr/bin/
endef

$(eval $(call BuildPackage,freediag))
