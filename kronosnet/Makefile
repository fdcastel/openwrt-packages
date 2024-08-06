#kronosnet
include $(TOPDIR)/rules.mk
 
PKG_NAME:=kronosnet
PKG_VERSION:=1.28
PKG_RELEASE:=1
 
PKG_SOURCE:=kronosnet-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/kronosnet/kronosnet/releases/download/v$(PKG_VERSION)/
PKG_HASH:=ea0d44fd7e891320378b419a38ca91c4edbcdc06e5b961aedabb4159d7e8150f
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:=openssl zstd liblz4 lzo xz bzip2 nss libqb libnl

include $(INCLUDE_DIR)/package.mk
 
define Package/kronosnet
  SECTION:=corosync
  CATEGORY:=Corosync
  TITLE:=kronosnet
  DEPENDS:=+libopenssl +liblz4 +liblzo +bzip2 +libnss +libnl +nspr +liblzma +libzstd
endef

define Build/Configure
  $(call Build/Configure/Default, --disable-libknet-sctp --disable-man --disable-hardening)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/* $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(1)/usr/lib/pkgconfig
	$(INSTALL_DIR) $(1)/usr/lib/kronosnet
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/kronosnet/*.so* $(1)/usr/lib/kronosnet
endef

define Package/kronosnet/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/lib*.so.* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/kronosnet
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/lib/kronosnet/*.so* $(1)/usr/lib/kronosnet
endef
 
$(eval $(call BuildPackage,kronosnet))