PKG_NAME = mdbtools
PKG_VERS = 0.7.1
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/brianb/mdbtools/archive/
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)
SRC_DIR= $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/

DEPENDS = cross/glib

HOMEPAGE = https://github.com/brianb/mdbtools
COMMENT  = MDB Tools - Read Access databases on *nix
LICENSE  = GPL

GNU_CONFIGURE = 1
CONFIGURE_ARGS = --disable-man --disable-gmdb2
ADDITIONAL_CFLAGS = 

PRE_CONFIGURE_TARGET = myPreConfigure

INSTALL_TARGET = myInstall

include ../../mk/spksrc.cross-cc.mk

.PHONY: myPreConfigure
myPreConfigure:
	$(RUN) autoreconf -i -f

.PHONY: myInstall
myInstall:
	$(RUN) $(MAKE) install DESTDIR=$(INSTALL_DIR)
