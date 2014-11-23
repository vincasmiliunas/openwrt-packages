include $(TOPDIR)/rules.mk

PKG_NAME:=lpty
PKG_VERSION:=1.1-1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.tset.de/downloads
PKG_MD5SUM:=bfff072ba9a090a38fbf4458875245c3

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lpty
	DEPENDS:=+lua
	URL:=http://www.tset.de/lpty/
endef

define Build/Configure
	cp Makefile-src $(PKG_BUILD_DIR)/Makefile
	$(call Build/Configure/Default,)
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(CP) $(PKG_BUILD_DIR)/lpty.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
