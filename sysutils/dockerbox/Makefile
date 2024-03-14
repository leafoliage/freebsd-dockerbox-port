PORTNAME=	dockerbox
PORTVERSION=	0.1.4
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

DISK_DISTNAME=	dockerbox-img
DISKVERSION=	0.1.1
MASTER_SITES=   https://github.com/leafoliage/freebsd-dockerbox/releases/download/disk-${DISKVERSION}/:diskimg
DISTFILES=	${DISK_DISTNAME}-${DISKVERSION}.tar.zstd:diskimg
WRKSRC_DISKIMG=	${WRKDIR}/${DISK_DISTNAME}-${DISKVERSION}

NO_BUILD=	yes

post-extract:
	@${MKDIR} ${WRKSRC}/share
	@${MV} ${WRKSRC_DISKIMG}/disk.img ${WRKSRC}/share
	@${MV} ${WRKSRC_DISKIMG}/device.map ${WRKSRC}/share

.include <bsd.port.mk>
