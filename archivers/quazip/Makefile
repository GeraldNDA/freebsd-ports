# Created by: Nicola Vitale <nivit@FreeBSD.org>
# $FreeBSD$

PORTNAME=	quazip
DISTVERSION=	0.7.6
CATEGORIES=	archivers
PKGNAMESUFFIX=	-${FLAVOR}

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Qt/C++ wrapper for ZIP/UNZIP package

LICENSE=	LGPL21

FLAVORS=	qt5 qt4
FLAVOR?=	${FLAVORS:[1]}

USES=		cmake
USE_GITHUB=	yes
GH_ACCOUNT=	stachenov
USE_LDCONFIG=	yes

.  if ${FLAVOR} == qt4
DEPRECATED=	Qt4 has been EOL since december 2015
EXPIRATION_DATE=2019-03-15
USES+=		qt:4
USE_QT=		corelib moc_build network_build qmake_build rcc_build uic_build
CMAKE_ARGS=	-DBUILD_WITH_QT4:BOOL=TRUE
.  else
USES+=		compiler:c++11-lang qt:5
USE_QT=		core buildtools_build qmake_build
CMAKE_ARGS=	-DBUILD_WITH_QT4:BOOL=FALSE
QTVER_SUFFIX=	5
.  endif

PLIST_SUB=	QTVER_SUFFIX="${QTVER_SUFFIX}"

.include <bsd.port.mk>
