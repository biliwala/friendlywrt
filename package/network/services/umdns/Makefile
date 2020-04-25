#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=umdns
PKG_RELEASE:=1

PKG_SOURCE_URL=$(PROJECT_GIT)/project/mdnsd.git
PKG_SOURCE_PROTO:=git
<<<<<<< HEAD
<<<<<<< HEAD
PKG_SOURCE_DATE:=2018-01-02
PKG_SOURCE_VERSION:=78974417e182a3de8f78b7d73366ec0c98396b6c
PKG_MIRROR_HASH:=a60f9eb9428ac3256cd7c3c6d4207c116cedf4d212b82e2f86c1bf7c7898fcbb
=======
PKG_SOURCE_DATE:=2020-04-20
PKG_SOURCE_VERSION:=e74a3f9883199e9db7220d52b78e5fbdb4441ca3
PKG_MIRROR_HASH:=a54410a6407c3dad985c94e3ca6f9c2bb5786876c9545cf65a56e4dfc2b380ff
>>>>>>> b71c7c261b... umdns: update to version 2020-04-20
=======
PKG_SOURCE_DATE:=2020-04-25
PKG_SOURCE_VERSION:=cdac0460ba50dc45735f0be2e19a5a8efc3dafe1
PKG_MIRROR_HASH:=261cb929dfc03c1f293156cfdec8c2cd1541dcdc57ae42a323f9df5d26e6f7d2
>>>>>>> 4e5a29827f... umdns: update to version 2020-04-25

PKG_MAINTAINER:=John Crispin <john@phrozen.org>
PKG_LICENSE:=LGPL-2.1

include $(INCLUDE_DIR)/package-seccomp.mk
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/umdns
  SECTION:=net
  CATEGORY:=Network
  TITLE:=OpenWrt Multicast DNS Daemon
  DEPENDS:=+libubox +libubus +libblobmsg-json
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include

define Package/umdns/conffiles
/etc/config/umdns
endef

define Package/umdns/install
	$(INSTALL_DIR) $(1)/usr/sbin $(1)/etc/init.d $(1)/etc/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/umdns $(1)/usr/sbin/
	$(INSTALL_BIN) ./files/umdns.init $(1)/etc/init.d/umdns
	$(INSTALL_CONF) ./files/umdns.config $(1)/etc/config/umdns
	$(call InstallSeccomp,$(1),./files/umdns.json)
endef

$(eval $(call BuildPackage,umdns))
