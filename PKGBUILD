# Maintainer:
# Contributor: Alexander Rødseth <rodseth@gmail.com>
# Contributor: Tobias Powalowski <tpowa@archlinux.org>

pkgname=kradio
pkgver=4.0.7
pkgrel=1
arch=('x86_64' 'i686')
license=('GPL2')
pkgdesc='Comfortable KDE internet and AM/FM radio application'
url='http://kradio.sourceforge.net/'
depends=('kdebase-runtime' 'lirc-utils' 'libmms' 'ffmpeg')
makedepends=('automoc4' 'cmake' 'boost')
install="$pkgname.install"
source=("http://downloads.sourceforge.net/$pkgname/kradio4-$pkgver.tar.bz2")
sha256sums=('53d1a706f08cfd5a405142cf34cf9c0b03397b03961936651dfae7206003959c')

build() {
  cd "$srcdir"

  mkdir build
  cd build
  cmake "../${pkgname}4-$pkgver" \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd "$srcdir/build"

  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
