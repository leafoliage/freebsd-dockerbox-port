PORTNAME=	dockerbox
PORTVERSION=	0.1.3
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

NO_BUILD=	yes

DISK_DISTNAME=	dockerbox-img
DISKVERSION=	0.1.1
MASTER_SITES=	https://github.com/leafoliage/freebsd-dockerbox/releases/download/disk-0.1.1/:diskimg
DISTFILES=	${DISK_DISTNAME}-${DISKVERSION}.tar.zstd:diskimg 
WRKSRC_DISKIMG=	${WRKDIR}/${DISK_DISTNAME}-${DISKVERSION}	

post-extract:
	@${MKDIR} ${WRKSRC}/share
	@${MV} ${WRKSRC_DISKIMG}/disk.img ${WRKSRC}/share
	@${MV} ${WRKSRC_DISKIMG}/device.map ${WRKSRC}/share

.include <bsd.port.mk>
