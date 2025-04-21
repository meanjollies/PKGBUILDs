# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=simdzone
pkgver=0.2.1
pkgrel=1
pkgdesc='Fast and standards compliant DNS presentation format parser'
arch=('x86_64')
url="https://github.com/NLnetLabs/${pkgname}"
license=('BSD')
makedepends=('cmake')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha256sums=('67142e81c543d8cc324bbac9bc64b41af790d897c3d2075dc36628a503580863')

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
