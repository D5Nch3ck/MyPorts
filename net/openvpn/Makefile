# $OpenBSD: Makefile,v 1.88 2018/03/06 12:44:29 d5nch3ck Exp $

DISTNAME   =	openvpn-2.4.6
PKGNAME    =	openvpn-openssl-2.4.6
REVISION   =	0
CATEGORIES =	net security

MAINTAINER =	D5Nch3ck  <d5nch3ck@disroot.org>
HOMEPAGE   =	https://openvpn.net/index.php/open-source/
COMMENT    =	easy-to-use, robust, and highly configurable VPN

# GPLv2 only
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB       += c lzo2
MASTER_SITES   = http://swupdate.openvpn.net/community/releases/

LIB_DEPENDS    = archivers/lzo2 \
                 archivers/lz4

BUILD_DEPEND   = security/openssl

#SEPARATE_BUILD= Yes
CONFIGURE_STYLE= gnu
USE_LIBTOOL    = gnu

#CONFIGURE_ARGS+= --enable-password-save

CONFIGURE_ENV   = OPENSSL_LIBS="-L${LOCALBASE}/lib/eopenssl -Wl,-rpath,${LOCALBASE}/lib/eopenssl -lssl -lcrypto" \
		          OPENSSL_CFLAGS="-I${LOCALBASE}/include/eopenssl/" --with-crypto-library=openssl \
		          CC="cc" CPPFLAGS="-I${LOCALBASE}/include" LDFLAGS="-L${LOCALBASE}/lib"

do-install:
	    ${INSTALL_PROGRAM} ${WRKSRC}/src/openvpn/openvpn ${PREFIX}/bin/openvpn-openssl

.include <bsd.port.mk>
