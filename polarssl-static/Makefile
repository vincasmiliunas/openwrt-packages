include $(TOPDIR)/rules.mk

PKG_NAME:=polarssl-static
PKG_VERSION:=1.3.9
PKG_RELEASE:=1
PKG_USE_MIPS16:=0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/polarssl/polarssl.git
PKG_SOURCE_VERSION:=82788fb63b7abc420e7d400f9d2948fd28add422
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_SOURCE_SUBDIR)-$(PKG_SOURCE_VERSION).tar.gz

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/$(PKG_NAME)
	SUBMENU:=SSL
  SECTION:=libs
  CATEGORY:=Libraries
	TITLE:=PolarSSL static build
	URL:=https://polarssl.org/
  ABI_VERSION:=$(PKG_VERSION)
endef

CMAKE_OPTIONS += -DCMAKE_POSITION_INDEPENDENT_CODE:Bool=ON
CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:String="Release"
CMAKE_OPTIONS += -DENABLE_TESTING:Bool=OFF
CMAKE_OPTIONS += -DENABLE_PROGRAMS:Bool=OFF

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/polarssl $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpolarssl.a $(1)/usr/lib/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
