# $FabBSD$
# $OpenBSD: Makefile,v 1.18 2007/12/30 20:15:37 espie Exp $

COMMENT=	perfect hash functions, to help write parsers

DISTNAME=	gperf-3.0.1
CATEGORIES=   	devel

# From OpenBSD:
#MAINTAINER=	Marc Espie <espie@openbsd.org>

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes
WANTLIB=		c m stdc++

MASTER_SITES=	${MASTER_SITE_GNU:=gperf/}

post-extract:
	rm ${WRKDIST}/doc/gperf.info

# Don't use SEPARATE_BUILD, the doc doesn't like it
CONFIGURE_STYLE=	gnu autoconf no-autoheader
AUTOCONF_VERSION=	2.57

# and it also insists upon installing under $(prefix)/doc...
MAKE_FLAGS=	docdir='${TRUEPREFIX}/share/doc/gperf'

# N.B. gperf is a build dependency for libiconv; take care if
# gettext support is added to gperf.
.include <bsd.port.mk>
