# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Marcin (CTRL) Wieczorek <marcin@marcin.co>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=execline
pkgver=2.9.9.1
pkgrel=1
pkgdesc='A (non-interactive) scripting language, like sh'
arch=('x86_64')
url="https://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs')
options=('!lto' '!debug')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('be63533297a93c36fd267195117b4e668687a526f834517a8db47d85b6c7ec6a'
            '45302cf9f817f1c8f2675a1e972454e630411c1fdabe208e0d43ba4c807afa3e')

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
