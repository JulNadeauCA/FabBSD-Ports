# $FabBSD$
# $OpenBSD: Makefile,v 1.20 2008/06/28 13:05:39 brad Exp $

COMMENT=		ARM/MIPS/PowerPC/SuperH machines emulator

DISTNAME=		gxemul-0.4.6.5
CATEGORIES=		emulators
HOMEPAGE=		http://gavare.se/gxemul/

# From OpenBSD:
#MAINTAINER=		Alexander Yurchenko <grange@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=		${HOMEPAGE}/src/

WANTLIB=		c m

CONFIGURE_STYLE=	simple

CONFIGURE_ARGS=		--disable-x

NO_REGRESS=		Yes

INSTALL_STRIP=

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/gxemul ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/gxemul
	${INSTALL_DATA} ${WRKSRC}/doc/*.{gif,png,html} \
		${PREFIX}/share/doc/gxemul
	${INSTALL_DATA} ${WRKSRC}/man/gxemul.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
