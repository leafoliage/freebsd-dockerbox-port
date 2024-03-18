PORTNAME=	dockerbox
PORTVERSION=	0.1.6
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils

MAINTAINER=	leafoliages@gmail.com
COMMENT=	Docker daemon inside virtualized Linux
WWW=		https://github.com/leafoliage/freebsd-dockerbox

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

ONLY_FOR_ARCHS=	amd64

RUN_DEPENDS=	grub2-bhyve>0:sysutils/grub2-bhyve

USE_GITHUB=	yes
GH_ACCOUNT=	leafoliage
GH_PROJECT=	freebsd-dockerbox

NO_BUILD=	yes

.include <bsd.port.mk>
