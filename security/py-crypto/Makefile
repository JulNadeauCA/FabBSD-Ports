# $FabBSD$
# $OpenBSD: Makefile,v 1.10 2008/06/11 02:59:32 wcmaier Exp $

SHARED_ONLY=		Yes

COMMENT=		cryptographic tools for Python

MODPY_EGG_VERSION=	2.0.1
DISTNAME=		pycrypto-${MODPY_EGG_VERSION}
PKGNAME=		py-crypto-${MODPY_EGG_VERSION}p4
CATEGORIES=    		security devel

HOMEPAGE=		http://www.amk.ca/python/code/crypto.html

# From OpenBSD:
#MAINTAINER=		Will Maier <wcmaier@openbsd.org>

# Public domain (patented algorithms removed by patch)
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	http://www.amk.ca/files/python/crypto/

MODULES=	lang/python
LIB_DEPENDS=	gmp.>=6::devel/gmp

DOCSDIR=	${PREFIX}/share/doc/py-crypto

SUBST_VARS+=	LOCALBASE

pre-configure:
	@${SUBST_CMD} ${WRKSRC}/setup.py

post-install:
	${INSTALL_DATA_DIR} ${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README ${DOCSDIR}

do-regress: fake
	cd ${WRKSRC} && ${MAKE_ENV} \
		PYTHONPATH=${WRKINST}${MODPY_SITEPKG} ${MODPY_BIN} test.py

.include <bsd.port.mk>
