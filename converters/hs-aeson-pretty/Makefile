# $FreeBSD$

PORTNAME=	aeson-pretty
PORTVERSION=	0.8.5
CATEGORIES=	converters haskell

MAINTAINER=	haskell@FreeBSD.org
COMMENT=	JSON pretty-printing library and command-line tool

LICENSE=	BSD3CLAUSE

USE_CABAL=	aeson attoparsec base-compat cmdargs scientific text \
		unordered-containers vector

FLAGS_DISABLE=	lib-only
EXECUTABLE=	aeson-pretty

.include "${.CURDIR}/../../lang/ghc/bsd.cabal.mk"
.include <bsd.port.mk>
