# $FabBSD$
# $OpenBSD: Makefile,v 1.4 2007/09/16 02:53:09 merdely Exp $

COMMENT=	thoroughly testing objects via registered handlers

MODULES=	cpan

DISTNAME=	Test-Object-0.07
CATEGORIES=	devel

# From OpenBSD:
#MAINTAINER=	Mathieu Sauve-Frankel <msf@openbsd.org>

# Artistic
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MAKE_ENV=	AUTOMATED_TESTING=Yes TEST_POD=Yes

.include <bsd.port.mk>
