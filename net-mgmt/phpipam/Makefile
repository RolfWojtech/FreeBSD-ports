# Created by: Jake Smith <jake@xz.cx>
# $FreeBSD$

PORTNAME=	phpipam
PORTVERSION=	1.2.1
CATEGORIES=	net-mgmt
MASTER_SITES=	SF/${PORTNAME}

MAINTAINER=	jake@xz.cx
COMMENT=	PHP IP Address Management IPv4/IPv6

LICENSE=	GPLv3

RUN_DEPENDS=	${LOCALBASE}/share/pear/System.php:devel/pear@${PHP_FLAVOR}

NO_BUILD=	yes
WRKSRC=		${WRKDIR}/${PORTNAME}

CFGFILE=	config.php

SUB_FILES=	pkg-message
SUB_LIST=	DISTNAME=${DISTNAME}

OPTIONS_DEFINE=	LDAP

USES=		gettext php:web tar:
USE_PHP=	ctype gettext gmp json mysqli pcntl session simplexml
LDAP_USE=	PHP=ldap

pre-install:
	@if [ -f ${WRKSRC}/${CFGFILE} ]; then \
	${MV} ${WRKSRC}/${CFGFILE} ${WRKSRC}/${CFGFILE}.sample ; \
	fi

do-install:
	cd ${WRKSRC} ; \
	for src in $$( ${FIND} . ! -name '*.orig') ; do \
		dst=${STAGEDIR}${WWWDIR}$${src#.} ; \
		if ${TEST} -d "$$src" ; then \
			${MKDIR} "$$dst" ; \
		else \
			${INSTALL_DATA} "$$src" "$$dst" ; \
		fi \
	done

.include <bsd.port.mk>
