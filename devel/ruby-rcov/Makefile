# $FabBSD$
# $OpenBSD: Makefile,v 1.3 2008/06/14 23:46:38 landry Exp $

SHARED_ONLY=	Yes

COMMENT=	code coverage tool for Ruby

DISTNAME=	rcov-0.8.1.2.0
PKGNAME=	ruby-${DISTNAME}p0
CATEGORIES=	devel

# From OpenBSD:
#MAINTAINER=	Markus Friedl <markus@openbsd.org>

# MIT License
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	${MASTER_SITE_RUBYFORGE:=rcov/}

MODULES=	lang/ruby

WANTLIB=	c m

LIB_DEPENDS=	ruby::lang/ruby

CONFIGURE_STYLE=ruby gem

.include <bsd.port.mk>
