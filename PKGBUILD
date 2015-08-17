# Maintainer: lluixhi <lluixhi@gmail.com>
pkgname=toxgui-git
pkgver=259.eb3ffc3
pkgrel=1
pkgdesc="A QT GUI for Tox"
arch=('i686' 'x86_64')
url="https://github.com/tux3/toxgui"
license=('GPL')
makedepends=('git')
depends=('qt5-multimedia' 'tox-git' 'libvpx')
conflicts=('toxgui')
provides=('toxgui')
options=()
source=("$pkgname"::'git+https://github.com/tux3/toxgui.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "$srcdir/$pkgname"

  mkdir build && cd build
  qmake-qt5 ..
  make
}

package() {
  mkdir -p "$pkgdir/usr/bin"
  install -m755 -p -s "$srcdir/$pkgname/build/toxgui" "$pkgdir/usr/bin/toxgui"
}

# vim:set ts=2 sw=2 et:
