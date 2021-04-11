#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ices
PKG_VERSION:=0.4
PKG_RELEASE:=

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://downloads.xiph.org/releases/ices/
PKG_HASH:=6e71f7c2a5d7415565a3af4f4c688ada4915312714c74bb7567f2b4b6d183074

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Nicolas Thill <nico@openwrt.org>, \
		Ted Hess <thess@kitschensync.net>

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/ices0
  SECTION:=sound
  CATEGORY:=Sound
  TITLE:=ices 0.4 client for Icecast media streaming servers
  URL:=http://www.icecast.org/ices/
  DEPENDS:=+libshout \
  +libxml2 \
  +zlib 
  #+libogg +libvorbis +alsa-lib 
   $(ICONV_DEPENDS)
endef

define Package/ices0/description
  ices is a command line source client for Icecast media streaming servers.
  It began as the successor of the old "shout" utility, and has since gained a
  lot of useful features.
endef

#CONFIGURE_ARGS+= \
#	--with-ogg="$(STAGING_DIR)/usr/include" \
#	--with-vorbis="$(STAGING_DIR)/usr/include"

TARGET_LDFLAGS+= -lvorbisidec
#-logg 

define Package/ices0/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/ices $(1)/usr/bin/
endef

$(eval $(call BuildPackage,ices0))
