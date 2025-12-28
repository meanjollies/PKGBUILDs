# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Marcin (CTRL) Wieczorek <marcin@marcin.co>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=execline
pkgver=2.9.8.0
pkgrel=1
pkgdesc='A (non-interactive) scripting language, like sh'
arch=('x86_64')
url="https://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs')
options=('!lto' '!debug')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('d05e0b75cc21841692119c7a7838163acd7f05318bd69e779068266daa7ce91f'
            '6682db386a057242d140d96f4dc0aca623dcb2aaab8d468f37c403e19079a8a2')

prepare() {
  patch -p0 -i ../${pkgname}.patch
}

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr --libdir=/usr/lib
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
  install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
