# $FabBSD$
# $OpenBSD: Makefile,v 1.30 2008/06/03 13:54:18 okan Exp $

ONLY_FOR_ARCHS= i386

COMMENT=	ANSI Common Lisp compiler

DISTNAME=	clisp-2.43
PKGNAME=	${DISTNAME}p0
CATEGORIES=	lang
HOMEPAGE=	http://clisp.cons.org/

# GPL
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MODULES=	devel/gettext

LIB_DEPENDS=	sigsegv::devel/libsigsegv
WANTLIB=	c m ncurses readline

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=clisp/}
EXTRACT_SUFX=	.tar.bz2

USE_LIBTOOL=	Yes
CONFIGURE_STYLE=gnu old
CONFIGURE_ARGS= --with-gmalloc \
		--srcdir=${WRKSRC} ${WRKBUILD}
SEPARATE_BUILD=	simple
MODGNU_CONFIG_GUESS_DIRS=	${WRKSRC}/ffcall/autoconf
USE_GMAKE=	Yes
MAKE_FLAGS=	INSTALL='install -c' \
		INSTALL_PROGRAM='install -c -s -m 555' \
		INSTALL_DATA='install -c -m 644'

post-configure:
	@cd ${WRKBUILD} && ./makemake \
		--fsstnd=openbsd \
		--prefix=${PREFIX} \
		--with-dynamic-ffi \
		--with-gmalloc \
		--mandir=${PREFIX}/man \
		--vimdir=${PREFIX}/share/doc/clisp \
		--docdir=${PREFIX}/share/doc/clisp >Makefile && \
	make config.lisp

.include <bsd.port.mk>
