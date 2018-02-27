#
# Copyright (C) 2014-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=netifaces
PKG_VERSION:=0.10.6
PKG_RELEASE:=1

https://pypi.python.org/packages/72/01/ba076082628901bca750bf53b322a8ff10c1d757dc29196a8e6082711c9d/netifaces-0.10.6.tar.gz#md5=1d424cb5ef52907c5ab913011122a98b
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/72/01/ba076082628901bca750bf53b322a8ff10c1d757dc29196a8e6082711c9d/
PKG_MD5SUM:=1d424cb5ef52907c5ab913011122a98b

PKG_BUILD_DEPENDS:=python3 python3-setuptools

PKG_LICENSE:=MIT

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-netifaces-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-netifaces
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Portable network interface information.
	URL:=https://bitbucket.org/al45tair/netifaces
	DEPENDS:=+python3-light +python3-setuptools
endef

define Package/python3-netifaces/description
	Portable network interface information.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="$(PKG_INSTALL_DIR)/usr" \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(PYTHON3_LIB_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON3_PKG_DIR)/* \
		$(PYTHON3_LIB_DIR)
endef

$(eval $(call Py3Package,python3-netifaces))
$(eval $(call BuildPackage,python3-netifaces))
