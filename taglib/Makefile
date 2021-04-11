#
# Copyright (C) 2010-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# https://taglib.org/releases/taglib-1.12.tar.gz

include $(TOPDIR)/rules.mk

PKG_NAME:=taglib
PKG_VERSION:=1.6
PKG_RELEASE:=

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://taglib.org/releases/
PKG_HASH:=9aa10e1544a7117d595103addacfdc4e29a055bfbfaa1666faa29990fb7fbd97

PKG_LICENSE:=LGPL
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Daniel Golle <daniel@makrotopia.org>

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/taglib
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=The library for reading and editing the meta-data
	URL:=https://taglib.org/
endef

define Package/taglib/description
	TagLib is a library for reading and editing the meta-data of several
	popular audio formats. Currently it supports both ID3v1 
	and ID3v2 for MP3 files, Ogg Vorbis comments and ID3 tags 
	and Vorbis comments in FLAC, MPC, Speex, WavPack, TrueAudio, WAV, 
	AIFF, MP4 and ASF files.
endef

define Package/taglib
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=The library for reading and editing the meta-data
	URL:=https://taglib.org/
	DEPENDS:=+libstdcpp +zlib
endef


define Package/taglib/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef


$(eval $(call BuildPackage,taglib))
