include $(TOPDIR)/rules.mk

PKG_NAME:=tcmalloc
PKG_VERSION:=2.7.0
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tcmalloc
	CATEGORY:=Libraries
	TITLE:=tcmalloc
	DEPENDS:=+libstdcpp +libunwind
endef

define Build/Configure
	( cd $(PKG_BUILD_DIR); ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Package/tcmalloc/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtcmalloc.so* $(1)/usr/lib
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtcmalloc.{a,so*} $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include
endef

$(eval $(call BuildPackage,tcmalloc))
