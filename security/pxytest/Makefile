# Created by: Paul Chvostek <paul@it.ca>
# $FreeBSD$

PORTNAME=	pxytest
PORTVERSION=	1.36
CATEGORIES=	security
MASTER_SITES=	http://www.unicom.com/files/
EXTRACT_SUFX=	.gz

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Test remote system for unsecured mail proxies

EXTRACT_CMD=	${GZIP_CMD}
EXTRACT_BEFORE_ARGS=	-dc
EXTRACT_AFTER_ARGS=	> ${WRKSRC}/${PORTNAME}

NO_WRKSUBDIR=	yes

USES=		perl5 shebangfix

PLIST_FILES=	bin/pxytest man/man1/pxytest.1.gz
SHEBANG_FILES=	pxytest

do-build:
	@cd ${WRKSRC} && pod2man ${PORTNAME} > ${PORTNAME}.1

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/${PORTNAME}.1 ${STAGEDIR}${MANPREFIX}/man/man1

.include <bsd.port.mk>
