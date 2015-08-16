# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kdeclarative
pkgver=4.99.0
pkgrel=1
pkgdesc='KDeclarative'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kdeclarative'
license=('LGPL')
depends=('kio')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('5fa7e3b7fbf2e9b143f1615e8c28a19e')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
