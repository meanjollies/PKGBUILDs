# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=s6
pkgver=2.15.1.0
pkgrel=1
pkgdesc='A small suite of programs for UNIX, designed to allow process supervision'
arch=('x86_64')
url="https://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs' 'execline')
options=('!lto')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('eab9c46e22b66b16135f9a05ec68a0ea287d9060b84d10defaaa2caad158ab52'
            '49a2c8cad5a70cfb99d373eb8a7f97ed8e93c818c853d2995c0ed3ce6ff521b5')

prepare() {
  patch -p0 -i ../${pkgname}.patch
}

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr --bindir=/usr/bin --sbindir=/usr/bin
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
  install -Dm644 COPYING "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
