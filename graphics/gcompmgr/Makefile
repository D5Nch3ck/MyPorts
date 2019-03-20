# $OpenBSD: Makefile,v 1.1 2017/04/13 18:48:02 D5Nch3ck Exp $

DISTNAME	= gcompmgr-0.21
CATEGORIES	= graphics
MASTER_SITES	= http://sourceforge.net/projects/gcompmgr/files/gcompmgr/${DISTNAME}/
EXTRACT_SUFX	= .tar.gz

MAINTAINER	= D5Nch3ck <d5nch3ck@disroot.org>
HOMEPAGE	= http://sourceforge.net/projects/gcompmgr/
COMMENT		= Graphical front end for xcompmgr
LICENSE		= gnu-lgpl-v2.1

PERMIT_PACKAGE_CDROM=   Yes
WRKDIST         = ${WRKDIR}
WRKSRC 		= ${WRKDIR}/${PKGNAME}


BUILD_DEPENDS	= x11/gtk2mm

NO_CONFIGURE	= yes

CONFIGURE_STYLE = gnu
AUTOCONF_VERSION= 2.69
AUTOMAKE_VERSION= 1.9

CONFIGURE_ENV	= CC="cc" CXX="c++ --std=c++11 -Wno-null-dereference"

NO_TEST		= Yes

pre-configure:
		  cd ${WRKSRC}; export AUTOCONF_VERSION=${AUTOCONF_VERSION} \
			AUTOMAKE_VERSION=${AUTOMAKE_VERSION}; libtoolize --force --copy; \
			aclocal; automake --add-missing; autoconf

.include <bsd.port.mk>
