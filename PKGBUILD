# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Eric DeStefano <eric at ericdestefano dot com> 
# Contributor: Frederic Bezies <fredbezies at gmail dot com>
# Contributor: Boris Timofeev <mashin87@gmail.com>

pkgname=xroar
pkgver=1.6.4
pkgrel=1
pkgdesc='A Dragon and Tandy CoCo emulator'
arch=('x86_64')
license=('GPL-3.0-or-later')
url="https://www.6809.org.uk/${pkgname}"
depends=('gtk2' 'sdl2' 'libgl' 'libsndfile' 'gtkglext')
makedepends=('gendesk')
install=${pkgname}.install
source=("${url}/dl/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.png")
sha256sums=('d9361abc5ce63821bfce0c72a921a74bedc366856413f09221ce9592af45d8d5'
            '0c6e5def77c6ca809cd69ae518512a89bff335147b44eb9ffc898d7302a17a59')

prepare() {
  cd "${pkgname}-${pkgver}"

  gendesk --pkgname "${pkgname}" --pkgdesc "${pkgdesc}" --exec "/usr/bin/${pkgname}" -n
}

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
  install -Dm644 "../${pkgname}.png" "${pkgdir}/usr/share/pixmaps/${pkgname}.png"
  install -Dm644 "${pkgname}.desktop" "${pkgdir}/usr/share/applications/${pkgname}.desktop"
  install -dm644 "${pkgdir}/usr/share/${pkgname}/roms"
}
