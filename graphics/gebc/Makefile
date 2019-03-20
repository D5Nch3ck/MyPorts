# $OpenBSD: Makefile,v 1.1 2017/04/13 18:48:02 D5Nch3ck Exp $

DISTNAME	= gebc-1.07-src
PKGNAME		= gebc-1.07
CATEGORIES	= graphics
MASTER_SITES	= https://sourceforge.net/projects/balcomp/files/GNU%20Ballistics%20-%20Source/Version%201.07/
EXTRACT_SUFX	= .tar.gz

MAINTAINER	= D5Nch3ck <d5nch3ck@disroot.org>
HOMEPAGE	= http://sourceforge.net/projects/balcomp
COMMENT		= GNU Exterior Ballistics Computer
LICENSE		= gnu-lgpl-v2.1

PERMIT_PACKAGE_CDROM=   Yes
WRKDIST         = ${WRKDIR}
WRKSRC 		= ${WRKDIR}/${PKGNAME}

USE_GMAKE	= YES

BUILD_DEPENDS	= x11/fltk \
		  print/libharu

NO_CONFIGURE	= yes

CONFIGURE_STYLE = gnu
AUTOCONF_VERSION= 2.69
AUTOMAKE_VERSION= 1.9

CONFIGURE_ENV	= CC="cc" CXX="c++" CPPFLAGS="-I${LOCALBASE}/include \
			-I/usr/X11R6/include"

NO_TEST		= Yes

pre-configure:
		cd ${WRKSRC}; export AUTOCONF_VERSION=${AUTOCONF_VERSION} \
			AUTOMAKE_VERSION=${AUTOMAKE_VERSION}; autoreconf; \
			automake --add-missing; autoreconf

post-install:
		${INSTALL_PROGRAM} ${WRKSRC}/gebc ${PREFIX}/bin

.include <bsd.port.mk>
