# $FabBSD$
# $OpenBSD: Makefile,v 1.5 2008/07/08 23:02:31 sthen Exp $

COMMENT=	read and write gzip and zip files/buffers

MODULES=	cpan

DISTNAME=	IO-Compress-Zlib-2.011
CATEGORIES=	archivers

# From OpenBSD:
#MAINTAINER=	Giovanni Bechis <g.bechis@snb.it>

# perl
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

RUN_DEPENDS=	:p5-Compress-Raw-Zlib->=2.006:archivers/p5-Compress-Raw-Zlib \
		:p5-IO-Compress-Base->=2.006:archivers/p5-IO-Compress-Base

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/p5-IO-Compress-Zlib
	perl -pi -e 's,/usr/local/bin,/usr/bin,' ${WRKSRC}/examples/*
	cd ${WRKSRC}/examples && ${INSTALL_SCRIPT} * \
		${PREFIX}/share/examples/p5-IO-Compress-Zlib

.include <bsd.port.mk>
