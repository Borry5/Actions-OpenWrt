include $(TOPDIR)/rules.mk

PKG_NAME:=minieap
PKG_VERSION:=2.7
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/ysc3839/minieap/releases/download/v$(PKG_VERSION)
PKG_HASH:=skip

include $(INCLUDE_DIR)/package.mk

define Package/minieap
  SECTION:=net
  CATEGORY:=Network
  TITLE:=A minimal 802.1X client for Ruijie
  URL:=https://github.com/ysc3839/minieap
endef

define Package/minieap/description
 A minimal 802.1X client for Ruijie, based on libpcap.
endef

define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) -o $(PKG_BUILD_DIR)/minieap \
		$(PKG_BUILD_DIR)/minieap.c -lpcap
endef

define Package/minieap/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/minieap $(1)/usr/bin/
endef

$(eval $(call BuildPackage,minieap))
