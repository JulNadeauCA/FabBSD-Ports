# $FabBSD$
# $OpenBSD: Makefile,v 1.47 2008/04/18 14:52:25 naddy Exp $

COMMENT=	GNU version of the traditional tape archiver

DISTNAME=	tar-1.20
PKGNAME=	g${DISTNAME}
CATEGORIES=	archivers
HOMEPAGE=	http://www.gnu.org/software/tar/

# From OpenBSD:
#MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	${MASTER_SITE_GNU:=tar/}
EXTRACT_SUFX=	.tar.bz2

MODULES=	devel/gettext
RUN_DEPENDS=	::archivers/bzip2 ::archivers/lzma

CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	--program-prefix=g
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include" \
		LDFLAGS="-L${LOCALBASE}/lib ${LDSTATIC}" \
		DEFAULT_ARCHIVE=/dev/rst0 \
		DEFAULT_RMT_COMMAND=/etc/rmt
MODGNU_CONFIG_GUESS_DIRS=${WRKSRC}/build-aux

FLAVORS=	static
FLAVOR?=

.if ${FLAVOR:L:Mstatic}
LDSTATIC=	-static
MODULES=
BUILD_DEPENDS=	:gettext->=0.16.1:devel/gettext
CONFIGURE_ENV+=	SHLIBEXT=""
.else
LDSTATIC=
WANTLIB=	c
.endif

.include <bsd.port.mk>
