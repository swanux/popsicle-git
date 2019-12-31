# Maintainer: Swanux <dani@kolozsi.net> -> https://github.com/swanux

pkgname=popsicle-git
pkgver=0.1.5.r180.g4bbdffc
pkgrel=1
pkgdesc="Linux utility for flashing multiple USB devices in parallel, written in Rust"
url="https://github.com/pop-os/popsicle"
arch=(x86_64 i686 aarch64 armv7h)
license=(MIT)
depends=(gtk3)
makedepends=(git rust cargo help2man xorgproto)
provides=(popsicle)
conflicts=(popsicle)
source=("git+https://github.com/pop-os/popsicle.git")
sha256sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
  cd "${pkgname%-git}"
  make
}

package() {
  cd "${pkgname%-git}"
  make DESTDIR="${pkgdir}/" prefix=/usr install
  mkdir -p $pkgdir/usr/share/licenses/$pkgname/
  install LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
