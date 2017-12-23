# $Id$
# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: rebel <novakpetya at yahoo dot co dot uk>

pkgname=qt5pas
pkgver=2.6.svn56827
pkgrel=1
pkgdesc='Free Pascal Qt5 binding library updated by lazarus IDE'
arch=('x86_64')
url='https://svn.freepascal.org/svn/lazarus/trunk/lcl/interfaces/qt5/cbindings'
license=('LGPL3')
depends=('qt5-base' 'qt5-x11extras')
makedepends=('subversion')
source=("$pkgname::svn+https://svn.freepascal.org/svn/lazarus/trunk/lcl/interfaces/qt5/cbindings")
sha512sums=('SKIP')

pkgver() {
    cd "$pkgname"
    echo "$(cat qt5.pas | grep '{ Version :' | sed -e 's/.*\([0-9]\+\.[0-9]\+\).*/\1/').svn$(svnversion | tr -d [A-z])"
}

build() {
    cd "$pkgname"
	qmake-qt5 "QT += x11extras"
	make
}

package() {
    cd "$pkgname"
	make INSTALL_ROOT="$pkgdir" install
}
