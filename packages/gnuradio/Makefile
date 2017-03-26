include $(TOPDIR)/rules.mk

GIT_COMMIT_TSTAMP:=$(shell git log -n 1 --pretty=%at . )

PKG_NAME:=gnuradio
PKG_VERSION:=master
PKG_RELEASE:=$(GIT_COMMIT_TSTAMP)

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/gnuradio-$(PKG_VERSION)
PKG_SOURCE_URL:=git://github.com/gnuradio/gnuradio/archive/$(PKG_SOURCE)
PKG_MD5SUM:=805540737e3c40a7c29b31ec2b9d01c5

include $(INCLUDE_DIR)/package.mk

define Package/gnuradio
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GNU Radio
  URL:=http://gnuradio.org/
endef

define Package/gnuradio/description
 Neat stuff with radios
endef

define Build/Configure
  $(call Build/Configure/Default,--with-linux-headers=$(LINUX_DIR))
endef

define Package/gnuradio/install
        $(INSTALL_DIR) $(1)/usr/sbin
        $(INSTALL_BIN) $(PKG_BUILD_DIR)/brctl/brctl $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,gnuradio))
