#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ezstream
PKG_VERSION:=1.0.2
PKG_RELEASE:=

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://ftp.osuosl.org/pub/xiph/releases/ezstream/
PKG_HASH:=11de897f455a95ba58546bdcd40a95d3bda69866ec5f7879a83b024126c54c2a

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Nicolas Thill <nico@openwrt.org>, Ted Hess <thess@kitschensync.net>

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/ezstream
  SECTION:=sound
  CATEGORY:=Sound
  TITLE:=ezstream client for Icecast media streaming servers
  URL:=http://www.icecast.org/ezstream/
  DEPENDS:=+libshout +check \
  +libxml2 \
  +zlib \
  #+libogg +libvorbis +alsa-lib 
  $(ICONV_DEPENDS)
endef

define Package/ezstream/description
  ezstream is a command line source client for Icecast media streaming servers.
  It began as the successor of the old "shout" utility, and has since gained a
  lot of useful features.
endef

CONFIGURE_ARGS+=''
#	--with-ogg="$(STAGING_DIR)/usr/include" \
#	--with-vorbis="$(STAGING_DIR)/usr/include"

#TARGET_LDFLAGS+=-rpath-link $(shell find $(STAGING_DIR) -name ld-uClibc.so.0)
TARGET_LDFLAGS+= -lvorbisidec
#-logg
	

define Package/ezstream/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/ezstream $(1)/usr/bin/
endef

$(eval $(call BuildPackage,ezstream))
