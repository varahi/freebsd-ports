# Created by: vassilis
# $FreeBSD$

PORTNAME=	flashplugin
PORTVERSION=	11.2.202.400
PACKAGE_PATH=	11_2r202_400
CATEGORIES=	www multimedia linux
MASTER_SITES=	http://download.macromedia.com/pub/flashplayer/installers/archive/

PKGNAMEPREFIX=	linux-f20-
DISTFILES=	fp_${PORTVERSION}_archive.zip


MAINTAINER=	vassilis@einval.com
COMMENT=	Adobe Flash Player NPAPI Plugin

ONLY_FOR_ARCHS=	amd64 i386
LINUX_CPU_ARCH=	i386
USE_LINUX=	f20
#USE_LINUX_APPS=	openssl curl cyrus-sasl2 libssh2 nspr nss openldap gtk2
#WANT_GNOME=	yes
DISTINFO_FILE?=		${MASTERDIR}/distinfo.${LINUX_CPU_ARCH}
NO_BUILD=	yes

RESTRICTED=	Redistribution not allowed
#RESTRICTED_FILES=	${DISTFILES:Nlinux-f10-flashsupport*:C/:[^:]+$//}

NO_WRKSUBDIR=	yes

USES=		webplugin
WEBPLUGIN_FILES=	libflashplayer.so

#OPTIONS_DEFINE=	GNOME
#GNOME_DESC=	include gnome support for .desktop file

OPTIONS_SUB=	yes
PLIST_SUB+=RESETPREFIX=${PREFIX}

.include <bsd.port.options.mk>

#.if ${PORT_OPTIONS:MGNOME}
#USES+=		desktop-file-utils
#INSTALLS_ICONS=	yes
#.endif

pre-patch:
	@cd ${WRKDIR}/
	@tar -xzf $p_${PORTVERSION}_archive/${PACKAGE_PATH}_32bit/flashplayer_${PACKAGE_PATH}_linux.${LINUX_CPU_ARCH}.tar.gz

#post-patch:
	#@${REINPLACE_CMD} -e 's|/usr|${PREFIX}|' -e '/^NotShowIn=KDE/d' ${WRKDIR}/usr/share/applications/flash-player-properties.desktop

do-install:
	#${MKDIR} ${STAGEDIR}${WEBPLUGIN_DIR} ${STAGEDIR}${LINUXBASE}/usr/lib
	#${INSTALL_LIB} ${WRKDIR}/libflashplayer.so ${STAGEDIR}${WEBPLUGIN_DIR}
	#${INSTALL_LIB} ${WRKDIR}/libflashsupport.so ${STAGEDIR}${LINUXBASE}/usr/lib
	#${INSTALL_PROGRAM} ${WRKDIR}/usr/bin/flash-player-properties ${STAGEDIR}${PREFIX}/bin
	#${INSTALL_DATA} ${WRKDIR}/usr/share/applications/flash-player-properties.desktop ${STAGEDIR}${DESKTOPDIR}
	#(cd ${WRKDIR}/usr/share/icons && ${COPYTREE_SHARE} hicolor ${STAGEDIR}${PREFIX}/share/icons)

.include <bsd.port.mk>
