PORTNAME=	dockerbox
PORTVERSION=	0.1.2
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils	

MAINTAINER=	leafoliages@gmail.com
COMMENT=	Docker daemon inside virtualized Linux
WWW=		https://github.com/leafoliage/freebsd-dockerbox

ONLY_FOR_ARCHS=	amd64

RUN_DEPENDS=	grub2-bhyve>0:sysutils/grub2-bhyve

USE_GITHUB=	yes
GH_ACCOUNT=	leafoliage
GH_PROJECT=	freebsd-dockerbox

MASTER_SITES=	https://github.com/leafoliage/freebsd-dockerbox/releases/download/disk-0.1.0/:diskimg
DISTFILES=	dockerbox-img.tar.gz:diskimg 

post-extract:
	@${MKDIR} ${WRKSRC}/share
	@${MV} ${WRKDIR}/disk.img ${WRKSRC}/share
	@${MV} ${WRKDIR}/device.map ${WRKSRC}/share

.include <bsd.port.mk>
