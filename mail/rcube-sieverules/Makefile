# $OpenBSD: Makefile,v 1.41 2011/08/16 08:29:13 sthen Exp $

COMMENT =	roundcube plugin: sieve rules (managesieve)

DISTNAME =	sieverules-1.14
PKGNAME =	rcube-${DISTNAME}
CATEGORIES =	mail www
HOMEPAGE =	http://www.tehinterweb.co.uk/roundcube/\#pisieverules

MAINTAINER =	Stuart Henderson <sthen@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes
PERMIT_PACKAGE_FTP =	Yes
PERMIT_DISTFILES_CDROM =Yes
PERMIT_DISTFILES_FTP =	Yes

MASTER_SITES =	http://spacehopper.org/mirrors/

NO_BUILD =	Yes
NO_REGRESS =	Yes
PKG_ARCH =	*

PREFIX =	/var/www
WRKDIST =	${WRKDIR}/sieverules
INSTDIR =	${PREFIX}/roundcubemail/plugins
TINSTDIR =	${TRUEPREFIX}/roundcubemail/plugins
SUBST_VARS =	INSTDIR TINSTDIR

MODULES =	lang/php
RUN_DEPENDS =	mail/roundcubemail>=0.6rc1

do-install:
	${INSTALL_DATA_DIR} ${INSTDIR}
	cp -Rp ${WRKDIST} ${INSTDIR}
	chown -R ${SHAREOWN}:${SHAREGRP} ${INSTDIR}
	find ${INSTDIR} \( -name \*.orig -or -name \*.src \) -exec rm -f {} \;

.include <bsd.port.mk>
