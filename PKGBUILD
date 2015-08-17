# Maintainer: Pat Brisbin <pbrisbin@gmail.com>
_gitname='rcm'
pkgname=$_gitname-git
pkgver=0.0.0
pkgrel=4
pkgdesc="rc file (dotfile) management"
arch=('any')
url="http://thoughtbot.github.io/rcm/"
license=('BSD')
conflicts=('rcm')
makedepends=('git' 'ruby-mustache')
source=('git://github.com/thoughtbot/rcm')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  git describe --long | sed -r 's/([^-]*-g)/r\1/;s/-/./g'
}

prepare() {
  cd "$srcdir/$_gitname"
  ./autogen.sh
}

build() {
  cd "$srcdir/$_gitname"
  ./configure \
    --disable-silent-rules \
    --prefix=/usr
  make
}

package() {
  cd "$srcdir/$_gitname"
  make DESTDIR="$pkgdir/" install
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$_gitname/LICENSE"
}

# vim:set ts=2 sw=2 et:
