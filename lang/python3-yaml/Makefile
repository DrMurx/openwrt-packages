#
# Copyright (C) 2014-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=PyYAML
PKG_VERSION:=3.12
PKG_RELEASE:=1

PKG_SOURCE:=PyYAML-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/4a/85/db5a2df477072b2902b0eb892feb37d88ac635d36245a72a6a69b23b383a/
PKG_MD5SUM:=4c129761b661d181ebf7ff4eb2d79950

PKG_LICENSE:=MIT

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-pyyaml-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-yaml
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Fast YAML parser
	URL:=http://pyyaml.org/wiki/PyYAML
	DEPENDS:=+python3-light
endef

define Package/python3-yaml/description
	Fast YAML parser.
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

$(eval $(call Py3Package,python3-yaml))
$(eval $(call BuildPackage,python3-yaml))
