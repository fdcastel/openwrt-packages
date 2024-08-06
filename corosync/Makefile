#corosync
include $(TOPDIR)/rules.mk
 
PKG_NAME:=corosync
PKG_VERSION:=3.1.8
PKG_RELEASE:=1
 
PKG_SOURCE:=corosync-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/corosync/corosync/releases/download/v$(PKG_VERSION)/
PKG_HASH:=7023544fa3bb36c00bbcabd9935b7269b41d896738a108ed32ea9b9c9b27ec3d
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:=libqb kronosnet
 
include $(INCLUDE_DIR)/package.mk
 
define Package/corosync
  SECTION:=corosync
  CATEGORY:=Corosync
  TITLE:=Corosync 
  DEPENDS:=+kronosnet +libqb
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/corosync
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/corosync/* $(1)/usr/include/corosync/
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(1)/usr/lib/pkgconfig
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef

define Package/corosync/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef
 
$(eval $(call BuildPackage,corosync))