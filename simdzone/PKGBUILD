# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=simdzone
pkgver=0.2.2
pkgrel=1
pkgdesc='Fast and standards compliant DNS presentation format parser'
arch=('x86_64')
url="https://github.com/NLnetLabs/${pkgname}"
license=('BSD')
makedepends=('cmake')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('b692d7cd722ead54f7d76190ad5827a7716c03e374b86166e4119913e51a98c6')

build() {
  cd "${pkgname}-${pkgver}"

  mkdir build
  cd build
  cmake -DCMAKE_BUILD_TYPE=Release ..
  cmake --build .
}

package() {
  cd "${pkgname}-${pkgver}"

  install -Dm755 build/zone-bench "${pkgdir}/usr/bin/zone-bench" 
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
