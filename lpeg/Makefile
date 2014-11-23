include $(TOPDIR)/rules.mk

PKG_NAME:=lpeg
PKG_VERSION:=0.12
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.inf.puc-rio.br/~roberto/lpeg
PKG_MD5SUM:=4abb3c28cd8b6565c6a65e88f06c9162

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lpeg
	DEPENDS:=+lua
	URL:=http://www.inf.puc-rio.br/~roberto/lpeg/
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(CP) $(PKG_BUILD_DIR)/lpeg.so $(1)/usr/lib/lua
	$(CP) $(PKG_BUILD_DIR)/re.lua $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
