# $FabBSD$
# $OpenBSD: Makefile,v 1.44 2008/06/08 17:16:06 simon Exp $

SHARED_ONLY=	Yes

COMMENT=	access to PostgreSQL databases through the DBI

MODULES=	cpan
DISTNAME=	DBD-Pg-2.7.2
CATEGORIES=	databases

LIB_DEPENDS=	pq.>=2:postgresql-client-*:databases/postgresql
RUN_DEPENDS=	::databases/p5-DBI \
		::devel/p5-version
BUILD_DEPENDS=	${RUN_DEPENDS}
REGRESS_DEPENDS=:postgresql-server-*:databases/postgresql,-server

REGRESS_FLAGS=	DBI_DSN="dbi:Pg:dbname=template1" DBI_USER="_postgresql" \
		DBI_PASS=""

# From OpenBSD:
#MAINTAINER=	Mathieu Sauve-Frankel <msf@openbsd.org> 

PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

CONFIGURE_ENV+=	POSTGRES_HOME="${LOCALBASE}" \
		POSTGRES_LIB="${LOCALBASE}/lib" \
		POSTGRES_INCLUDE="${LOCALBASE}/include/postgresql"

.include <bsd.port.mk>
