# $FabBSD$
# $OpenBSD: Makefile,v 1.12 2007/12/07 22:23:38 okan Exp $

COMMENT=	tool to indent and reformat perl scripts

V=	 	20071205
DISTNAME=	Perl-Tidy-$V
PKGNAME=	perltidy-$V
CATEGORIES=	devel

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=perltidy/}

HOMEPAGE=	http://perltidy.sourceforge.net/

# From OpenBSD:
#MAINTAINER=	Jim Razmus <jim@bonetruck.org>

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

CONFIGURE_STYLE=perl

PKG_ARCH=	*

DOCS=		tutorial.pod testfile.pl stylekey.pod

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/perltidy
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/perltidy
.for f in ${DOCS}
	${INSTALL_DATA} ${WRKSRC}/docs/${f} ${PREFIX}/share/doc/perltidy
.endfor
	${INSTALL_DATA} ${WRKSRC}/examples/* ${PREFIX}/share/examples/perltidy

.include <bsd.port.mk>
