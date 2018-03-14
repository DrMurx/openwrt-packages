include $(TOPDIR)/rules.mk

PKG_NAME:=python3-xknx
PKG_VERSION:=preview
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/DrMurx/xknx.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)

PKG_LICENSE=MIT

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-xknx
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=XKNX library
	URL:=https://xknx.io
	DEPENDS:=+python3-light +python3-netifaces +python3-yaml
endef

define Package/python3-xknx/description
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

$(eval $(call Py3Package,python3-xknx))
$(eval $(call BuildPackage,python3-xknx))
