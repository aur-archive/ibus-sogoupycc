# Contributor: WU Jun <quark at lihdd dot net>
# Maintainer: Daniel J Griffiths <ghost1227@archlinux.us>

pkgname=ibus-sogoupycc
pkgver=0.2.5
pkgrel=1
pkgdesc="A Sogou cloud client and Chinese input method on ibus platform. (deprecated)"
arch=('i686' 'x86_64')
url="http://code.google.com/p/ibus-sogoupycc/"
license=('GPL')
depends=('ibus' 'luasocket' 'sqlite3' 'gtk2' 'libnotify')
makedepends=('cmake')
conflicts=('ibus-sogoupycc-svn')
source=(http://${pkgname}.googlecode.com/files/${pkgname}-${pkgver}.tar.gz \
	http://ibus-sogoupycc.googlecode.com/files/open-phrase-201003.tar.gz)
md5sums=('ede455234e7d51849ab8258e139a7ae6'
         '64c29758b2837ef0c70d823a3b31ec3e')

build() {
	cd ${srcdir}/${pkgname}-${pkgver}
	./build.sh || return 1
}

package() {
	cd ${srcdir}/${pkgname}-${pkgver}/build
	make DESTDIR=${pkgdir} install || return 1
	install -Dm644 ${srcdir}/db/main.db \
		${pkgdir}/usr/share/ibus-sogoupycc/db/main.db
}


