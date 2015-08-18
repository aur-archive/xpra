# Contributor: Bug <bug2000@gmail.com>
# Contributor: Niels Martignène <niels.martignene@gmail.com>
# Maintainer: Niels Martignène <niels.martignene@gmail.com>
pkgname=xpra
pkgver=0.3.1
pkgrel=1
pkgdesc="Screen for X"
arch=('i686' 'x86_64')
url='http://xpra.org/'
license=('GPL2')
depends=('python2' 'pygtk' 'libxtst' 'xorg-server-xvfb' 'python-imaging')
conflicts=('parti-all')
provides=('parti-all')
makedepends=('setuptools' 'cython2')
source=("http://xpra.org/src/xpra-$pkgver.tar.bz2")
md5sums=('d55d08bec2ee61a1f1c40cc7114d080e')

build() {
    cd ${srcdir}/xpra-$pkgver

    python2 make_constants_pxi.py wimpiggy/lowlevel/constants.txt wimpiggy/lowlevel/constants.pxi
    python2 setup.py build || return 1
}

package() {
    cd ${srcdir}/xpra-$pkgver

    python2 setup.py install --root=${pkgdir} || return 1
}
