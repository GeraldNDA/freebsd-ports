# Created by: Marc van Woerkom <3d@FreeBSD.org>
# $FreeBSD$

PORTNAME=	libdvdread
PORTVERSION=	6.0.0
CATEGORIES=	multimedia
MASTER_SITES=	http://download.videolan.org/pub/videolan/libdvdread/${PORTVERSION}/ \
		http://dvdnav.mplayerhq.hu/releases/ \
		http://contribs.martymac.org/FreeBSD-ports/distfiles/ \
		LOCAL/martymac

MAINTAINER=	martymac@FreeBSD.org
COMMENT=	Videolan version of the libdvdread project

LICENSE=	GPLv2

GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USES=		tar:bz2 gmake libtool pathfix pkgconfig
USE_LDCONFIG=	yes

PORTDOCS=	AUTHORS COPYING ChangeLog NEWS README TODO

OPTIONS_DEFINE=	DVDCSS DOCS
.if !defined(PACKAGE_BUILDING)
OPTIONS_DEFAULT=	DVDCSS
.endif

# DVDCSS version hardcoded in src/dvd_input.c (dlopen'ed)
DVDCSS_LIB_DEPENDS=	libdvdcss.so.2:multimedia/libdvdcss

.include <bsd.port.mk>
