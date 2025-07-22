# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: EndlessEden <eden [at] rose.place>
# Contributor: Juri Grabowski <arch-dablin-maint@jugra.de>

pkgname=dablin
pkgver=1.16.0
pkgrel=1
pkgdesc='Plays a DAB/DAB+ audio service from a live transmission or from a stored ensemble recording'
arch=('x86_64')
url="https://github.com/Opendigitalradio/${pkgname}"
license=('GPL-3.0-only')
depends=('sdl2' 'mpg123' 'gtkmm3' 'faad2')
makedepends=('cmake')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
sha256sums=('3b008ed7a6f98802b7cfc7e753c4a6d68766a2d5a48b7ce68d3dce14ebf4cf03')

build() {
  local cmake_options=(
    -B build
    -S "${pkgname}-${pkgver}"
    -W no-dev
    -D CMAKE_BUILD_TYPE=Release
    -D CMAKE_INSTALL_PREFIX=/usr
    -D CMAKE_POLICY_VERSION_MINIMUM=3.5
  )

  cmake "${cmake_options[@]}"
  cmake --build build
}

package() {
  DESTDIR="${pkgdir}" cmake --install build
}
