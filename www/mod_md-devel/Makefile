# Created by: Bernard Spil <brnrd@FreeBSD.org>
# $FreeBSD$

PORTNAME=	mod_md-devel
PORTVERSION=	0.0.20170809
CATEGORIES=	www

MAINTAINER=	brnrd@FreeBSD.org
COMMENT=	Early experience LetsEncrypt module for Apache httpd

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libcurl.so:ftp/curl \
		libjansson.so:devel/jansson

USES=		autoreconf libtool ssl
USE_GITHUB=	yes
USE_APACHE=	24+

GH_ACCOUNT=	icing
GH_PROJECT=	mod_md
GH_TAGNAME=	1e07174

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--program-prefix=ext-
CONFIGURE_ENV=	CONFIG_SHELL=/bin/sh

MODULENAME=	${GH_PROJECT}

CFLAGS+=	-I${LOCALBASE}/include
CPPFLAGS+=	-I${LOCALBASE}/include

#DOCSDIR=	share/docs/mod_md
PORTDOCS=	README README.md
PLIST_FILES=	${APACHEMODDIR}/mod_md.so.0.0.0 \
		${APACHEMODDIR}/mod_md.so

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${APACHEMODDIR}/${MODULENAME}.so
	${MV} ${STAGEDIR}${PREFIX}/share/doc/mod_cert ${STAGEDIR}${PREFIX}/share/doc/mod_md-devel
	${RM} ${STAGEDIR}${PREFIX}/share/doc/mod_md-devel/LICENSE
	${RM} ${STAGEDIR}${PREFIX}/bin/ext-a2md

.include <bsd.port.mk>
