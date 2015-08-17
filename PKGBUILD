# Maintainer: Clément DEMOULINS <clement@archivel.fr>

pkgname=vaucanson-git
_realname=vaucanson
pkgver=v2b.3.r621.g74f6afb
pkgrel=1
pkgdesc="Finite state machine manipulation platform, consisting of a library and tools implemented on top of it."
arch=('i686' 'x86_64')
url="http://vaucanson.lrde.epita.fr/"
license=('GPL3')
depends=('boost' 'clang' 'ccache' 'libltdl' 'ipython')
makedepends=('git' 'texlive-core' 'doxygen' 'python2-docutils')
conflicts=('vaucanson')
provides=('vaucanson')

source=(git+https://gitlab.lrde.epita.fr/vcsn/vaucanson.git)
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${_realname}"
  git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
  cd "$srcdir/${_realname}"
  ./bootstrap
  ./configure --prefix="/usr"
  make V=1
}

package() {
  cd "$srcdir/${_realname}"
  make install DESTDIR="$pkgdir"
}

