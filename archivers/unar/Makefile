# $OpenBSD: Makefile,v 1.2 2017/04/13 18:48:02 D5Nch3ck Exp $

DISTNAME	= unar1.10.1_src
PKGNAME		= unarchiver-1.10.1
CATEGORIES	= archivers
MASTER_SITES	= http://wakaba.c3.cx/releases/TheUnarchiver/
EXTRACT_SUFX	= .zip

MAINTAINER	= D5Nch3ck <d5nch3ck@disroot.org>
HOMEPAGE	= http://unarchiver.c3.cx/commandline
COMMENT		= Command-line tools for The Unarchiver
LICENSE		= gnu-lgpl-v2.1

BUILD_DEPENDS	= audio/wavpack \
		  x11/gnustep/base

PERMIT_PACKAGE_CDROM=   Yes

WRKDIST         = ${WRKDIR}
WRKSRC 		= ${WRKDIR}/The*Unarchiver/XADMaster

USE_LANGUAGES	= c c++
USE_GMAKE	= YES

NO_CONFIGURE	= yes
MAKE_FILE	= Makefile.freebsd

NO_TEST         = Yes

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/??ar ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/../Extra/??ar.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
