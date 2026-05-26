# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Gavin Lloyd <gavinhungry@gmail.com>
# Contributor: Carsten Feuls <archlinux@carstenfeuls.de>

pkgname=klog
pkgver=2.5.2
pkgrel=1
pkgdesc='A multiplatform free hamradio logger'
arch=('x86_64')
url="https://github.com/ea4k/${pkgname}"
license=('GPL-3.0-only')
makedepends=('qt6-tools')
depends=('qt6-base' 'qt6-charts' 'qt6-declarative' 'qt6-location' 'qt6-serialport' 'hamlib')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('6648ddff9d068dcc3c66c34fad166c4fb1698c28f6b6db1351f28e2aab13c8c5')

build() {
  local cmake_options=(
    -B build
    -S "${pkgname}-${pkgver}"
    -W no-dev
    -D CMAKE_BUILD_TYPE=Release
    -D CMAKE_INSTALL_PREFIX=/usr
  )

  cmake "${cmake_options[@]}"
  cmake --build build
}

package() {
  DESTDIR="${pkgdir}" cmake --install build
}
