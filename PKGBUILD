pkgname=dillo
pkgver=3.0.5
pkgrel=1
pkgdesc="A small, fast graphical web browser built on FLTK"
arch=('x86_64')
url="http://www.dillo.org"
license=('GPL')
depends=('fltk' 'perl' 'openssl' 'libpng' 'gcc-libs' 'libxcursor'
         'libxi' 'libxinerama')
backup=(etc/dillo/{dillorc,dpidrc})
source=(http://www.dillo.org/download/$pkgname-$pkgver.tar.bz2)
sha256sums=('db1be16c1c5842ebe07b419aa7c6ef11a45603a75df2877f99635f4f8345148b')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sysconfdir=/etc --enable-cookies --enable-dlgui \
              --enable-ssl
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}