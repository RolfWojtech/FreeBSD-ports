# $FreeBSD$

PORTNAME=	jekyll-sitemap
PORTVERSION=	1.2.0
CATEGORIES=	textproc rubygems
MASTER_SITES=	RG

MAINTAINER=	ruby@FreeBSD.org
COMMENT=	Automatically generate a sitemap.xml for Jekyll sites

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.md

RUN_DEPENDS=	rubygem-jekyll>=3.3:www/rubygem-jekyll

NO_ARCH=	yes
USE_RUBY=	yes
USES=		gem shebangfix

SHEBANG_FILES=	script/*

.include <bsd.port.mk>
