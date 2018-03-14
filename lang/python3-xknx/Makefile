include $(TOPDIR)/rules.mk

PKG_NAME:=XKNX
PKG_VERSION:=0.0.1
PKG_RELEASE:=1

PKG_LICENSE:=MIT

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/DrMurx/xknx.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=preview
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

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
	XKNX library.
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/python3-xknx/install
	$(INSTALL_DIR) $(1)$(PYTHON3_PKG_DIR)
	$(CP) $(PKG_BUILD_DIR)/xknx $(1)$(PYTHON3_PKG_DIR)
endef

$(eval $(call BuildPackage,python3-xknx))
