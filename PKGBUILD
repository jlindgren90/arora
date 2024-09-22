# Maintainer: John Lindgren <john@jlindgren.net>

pkgname=arora
pkgver=0.11.0
pkgrel=1
pkgdesc='Cross-platform web browser using Qt WebKit'
arch=(x86_64)
url='https://github.com/Arora/arora/'
license=(GPL)
depends=(qt5-script qt5-webkit)
makedepends=(qt5-tools)

build() {
  cd ..
  # FIXME: prevent linking to Qt_5 versioned symbol std::bad_alloc
  qmake PREFIX=/usr QMAKE_CXXFLAGS_RELEASE="${CXXFLAGS} \
   -Wno-deprecated-declarations -fno-exceptions -fno-rtti"
  make
}

package() {
  cd ..
  INSTALL_ROOT="$pkgdir" make install
}
