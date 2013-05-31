# $NetBSD$
# #
#  
DISTNAME=       zeromq3-x
CATEGORIES=     # XXX: dunno, devel?
 
MAINTAINER=     pkgsrc-users@netbsd.org
HOMEPAGE=       https://github.com/zeromq/zeromq3-x
COMMENT=				The 0MQ lightweight messaging kernel is a library which extends the standard socket interfaces with features traditionally provided by specialised messaging middleware products. 
#LICENSE=       XXX: BSD-ish?
 
GIT_REPOSITORIES=       master
GIT_REPO.master=        git://github.com/zeromq/zeromq3-x.git
GIT_MODULE.master=      ${PKGBASE}
GIT_TAG.master=         v3.2
PKG_OPTIONS.=						

DEPENDS+= gtar>=1.26:../../archivers/gtar
DEPENDS+= libtool{,nb[0-9]*}:../../devel/libtool
 
GNU_CONFIGURE=  yes
USE_LANGUAGES=  c c++
USE_TOOLS+=     aclocal autoheader autoconf automake
WRKSRC=         ${WRKDIR}/${PKGBASE}-x
 
LIBS.SunOS+=    -lsocket -lnsl
 
pre-configure:
						cd ${WRKSRC} && \
								./autogen.sh && \
								${PREFIX}/bin/libtoolize -fc && \
								aclocal && \
								autoheader && \
								automake -ac && \
								autoconf
 
.include "../../devel/boost-libs/buildlink3.mk"
.include "../../wip/mk/git-package.mk"
.include "../../mk/bsd.pkg.mk"
