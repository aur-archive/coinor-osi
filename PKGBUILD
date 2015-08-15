pkgname=coinor-osi
pkgver=0.106.10
pkgrel=1
pkgdesc="COIN-OR Open Solver Interface"
arch=('any')
url="https://projects.coin-or.org/Osi"
license=('EPL')
groups=('coinor')
depends=('coinor-utils')
source=("http://www.coin-or.org/download/source/Osi/Osi-${pkgver}.tgz")
sha1sums=('eb92c2a4ae4cbb735c19ccd596a1337dc813a66d')


build() {
  cd Osi-$pkgver
  COIN_SKIP_PROJECTS="Sample" \
  ./configure --prefix=/usr -C \
              --with-coinutils-lib="$(pkg-config --libs coinutils)" \
              --with-coinutils-incdir="/usr/include/coin/" -C
  make
}

package() {
  cd "$srcdir/Osi-$pkgver"
  PKG_CONFIG_LIBDIR="${pkgdir}/usr/lib/pkgconfig/" \
  make DESTDIR="$pkgdir" install
}
