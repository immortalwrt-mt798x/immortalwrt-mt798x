# Copyright (C) 2016 LEDE project

include $(TOPDIR)/rules.mk

PKG_NAME:=openwrt-keyring
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/immortalwrt-mt798x/keyring.git
PKG_SOURCE_DATE:=2024-04-12
PKG_SOURCE_VERSION:=cabdd3bbbcf97e685535241356ee581c1734bb1f
PKG_MIRROR_HASH:=4d0aaa268d0829d81a9a1e3eaa0b011d3c467104083663899e7e4d86c437e91b

PKG_MAINTAINER:=John Crispin <john@phrozen.org>
PKG_LICENSE:=GPL-2.0

include $(INCLUDE_DIR)/package.mk

define Package/openwrt-keyring
  SECTION:=base
  CATEGORY:=Base system
  PROVIDES:=lede-keyring
  TITLE:=ImmortalWrt Developer Keyring
  URL:=https://openwrt.org/docs/guide-user/security/signatures
endef

define Package/openwrt-keyring/description
  The keyring of with the developer using and gpg public keys.
endef

Build/Compile=

define Package/openwrt-keyring/install
	$(INSTALL_DIR) $(1)/etc/opkg/keys/
	# Public usign key for OPDE
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/usign/66ceb3e8f7432fed $(1)/etc/opkg/keys/
	# Public usign key for 21.02 release builds
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/usign/2f8b0b98e08306bf $(1)/etc/opkg/keys/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/usign/1d072ccfc904f10a $(1)/etc/opkg/keys/
	# Public usign key for immortalwrt-mt798x 21.02 release builds
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/usign/6d24af202ebd299c $(1)/etc/opkg/keys/
endef

$(eval $(call BuildPackage,openwrt-keyring))
