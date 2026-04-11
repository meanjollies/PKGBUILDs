# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Shaw <puxx@mail.ustc.edu.cn>
# Contributor: Nick <iglu.sitar at gmail dot com>
# Contributor: Angus Gibson <darthshrine@gmail.com>

pkgname=ipbt
pkgver=20260410.a852474
pkgrel=1
pkgdesc='A high-tech ttyrec player'
arch=('x86_64')
url="https://www.chiark.greenend.org.uk/~sgtatham/${pkgname}"
license=('MIT')
depends=('ncurses' 'perl')
makedepends=('cmake')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('0713f515794643d48c88e79429dc392741e2ae15093b8d92bfc189110228406a'
            'a61024642f0d591307e0871693fa4677ee245c5e9d8b1d44f9159dc47b597225')

prepare() {
  patch -p0 -i ../${pkgname}.patch
}

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
  
  install -Dm755 "${srcdir}/${pkgname}-${pkgver}/ttydump" "${pkgdir}/usr/bin/ttydump"
  install -Dm755 "${srcdir}/${pkgname}-${pkgver}/ttygrep" "${pkgdir}/usr/bin/ttygrep"
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/ipbt.1" "${pkgdir}/usr/share/man/man1/ipbt.1"
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/LICENCE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENCE"
}
