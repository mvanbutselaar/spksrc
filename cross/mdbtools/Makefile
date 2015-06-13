PKG_NAME = mdbtools
PKG_VERS = 0.6
#0.6pre2-r2
PKG_EXT = tar.gz
# ftp://ftp.dvo.ru/pub/Gentoo/distfiles/mdbtools-cvs-20050624.tar.gz
PKG_DIST_NAME = mdbtools-cvs-20050624.$(PKG_EXT)
PKG_DIST_SITE = ftp://ftp.dvo.ru/pub/Gentoo/distfiles/
#PKG_DIR = $(PKG_NAME)-$(PKG_VERS)
PKG_DIR = mdbtools-cvs-20050624
#SRC_DIR= $(WORK_DIR)/$(PKG_NAME)-$(PKG_VERS)/
SRC_DIR= $(WORK_DIR)/mdbtools-cvs-20050624/

DEPENDS = cross/glib cross/libtool

HOMEPAGE = https://github.com/brianb/mdbtools
COMMENT  = MDB Tools - Read Access databases on *nix
LICENSE  = GPL

# work-88f6281-5.1/install/usr/local/mdbtools/lib/glib-2.0/include/glibconfig.h 
GNU_CONFIGURE = 1
CONFIGURE_ARGS = --disable-gmdb2
ADDITIONAL_CFLAGS = -I$(WORK_DIR)/glib-2.38.2

PRE_PATCH_TARGET = myPrePatch

#PRE_CONFIGURE_TARGET = myPreConfigure

INSTALL_TARGET = myInstall

include ../../mk/spksrc.cross-cc.mk

.PHONY: myPrePatch
myPrePatch:
	sed -i'' '21,29 s/^/#/' $(WORK_DIR)/mdbtools-cvs-20050624/autogen.sh
	@$(RUN) ; NOCONFIGURE=yes ACLOCAL_FLAGS="-I $(WORK_DIR)/install/usr/local/mdbtools/share/aclocal/" ./autogen.sh

#.PHONY: myPreConfigure
#myPreConfigure:
#	@$(RUN) ; ./autogen.sh

.PHONY: myInstall
myInstall:
	$(RUN) $(MAKE) install DESTDIR=$(INSTALL_DIR)
