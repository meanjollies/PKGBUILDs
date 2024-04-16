# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Marcin (CTRL) Wieczorek <marcin@marcin.co>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=execline
pkgver=2.9.5.0
pkgrel=2
pkgdesc='A (non-interactive) scripting language, like sh'
arch=('x86_64')
url="http://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs')
options=('!lto')
source=("${url}/${pkgname}-${pkgver}.tar.gz")
sha256sums=('c1eb0d3a2f4e9f5751452631617a147f532ac2dd4a07c564e33f1612d2de837e')

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
