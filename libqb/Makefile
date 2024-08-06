#libqb
include $(TOPDIR)/rules.mk
 
PKG_NAME:=libqb
PKG_VERSION:=2.0.8
PKG_RELEASE:=1
 
PKG_SOURCE:=libqb-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/ClusterLabs/libqb/releases/download/v$(PKG_VERSION)/
PKG_HASH:=4832d0c1f12be38cbcf608585758d4a3124def253a3914b61afeebc68484311e
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:=libxml2
 
include $(INCLUDE_DIR)/package.mk
 
define Package/libqb
  SECTION:=corosync
  CATEGORY:=Corosync
  TITLE:=libqb
  DEPENDS:=+libxml2
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/qb
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/qb/* $(1)/usr/include/qb
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(1)/usr/lib/pkgconfig
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef

define Package/libqb/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so.* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef
 
$(eval $(call BuildPackage,libqb))