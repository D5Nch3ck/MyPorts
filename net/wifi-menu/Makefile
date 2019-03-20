# $OpenBSD: Makefile,v 1.1 2018/04/13 18:48:02 D5Nch3ck Exp $

DISTNAME     = wifi-menu
V            = 2.0
PKGNAME      = ${DISTNAME}-${V}
DISTFILES    = master.zip
REVISION     = 1
CATEGORIES   = net
MASTER_SITES = https://github.com/D5Nch3ck/wifi-menu/archive/
EXTRACT_SUFX = .zip

MAINTAINER   = D5Nch3ck <d5nch3ck@disroot.org>
HOMEPAGE     = http://github.com/D5Nch3ck/wifi-menu
COMMENT      = OpenBSD Wireless network manager
LICENSE      = gnu-lgpl-v2.1

PERMIT_PACKAGE_CDROM=   Yes

WRKDIST      = ${WRKDIR}
WRKSRC       = ${WRKDIR}/${DISTNAME}-master
NO_BUILD     = Yes
PKG_ARCH     = *

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/wifi-menu \
		${PREFIX}/bin

.include <bsd.port.mk>
