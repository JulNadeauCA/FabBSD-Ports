# $FabBSD$
# $OpenBSD: Makefile,v 1.16 2007/09/16 02:53:09 merdely Exp $

SHARED_ONLY=		Yes

COMMENT=		change terminal modes, and perform non-blocking reads

MODULES=		cpan
V=			2.30
DISTNAME=		TermReadKey-${V}
PKGNAME=		p5-Term-ReadKey-${V}p0
CATEGORIES=		devel

# From OpenBSD:
#MAINTAINER=		Peter Stromberg <wilfried@openbsd.org>

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=		${MASTER_SITE_PERL_CPAN:=Term/}

REGRESS_IS_INTERACTIVE=	Yes

.include <bsd.port.mk>
