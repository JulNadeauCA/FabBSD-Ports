# $FabBSD$
# $OpenBSD: Makefile,v 1.20 2008/07/25 20:25:59 sthen Exp $

COMMENT=	Apache Portable Runtime

V=		1.3.7
DISTNAME=	apr-$V
FULLPKGNAME=	apr${MT}-$Vp2
SHARED_LIBS +=	apr-1${MT}             3.7

CATEGORIES=	devel

# From OpenBSD:
#MAINTAINER=	Aleksander Piotrowski <alek@openbsd.org>

HOMEPAGE=	http://apr.apache.org/

# Apache License 2.0
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	${MASTER_SITE_APACHE:=apr/}

USE_LIBTOOL=	Yes
CONFIGURE_STYLE=gnu
CONFIGURE_ARGS=	${CONFIGURE_SHARED} \
		--includedir=${LOCALBASE}/include/apr-1${MT}/ \
		--with-installbuilddir=${LOCALBASE}/lib/apr-1${MT}/ \
		--enable-other-child

FLAVORS=	mt
FLAVOR?=

SUBST_VARS+=	MT

.if ${FLAVOR:L:Mmt}
MT=-mt
CONFIGURE_ARGS+=	--enable-threads

post-install:
	sed 's/{APR_LIBNAME}/{APR_LIBNAME}-mt/g' ${WRKSRC}/apr-config.out > ${PREFIX}/bin/apr-1-mt-config

.else
MT=
CONFIGURE_ARGS+=	--disable-threads
.endif
MAKE_ENV+=	MT=${MT}

pre-install:
	rm -f ${WRKSRC}/libtool

.include <bsd.port.mk>
