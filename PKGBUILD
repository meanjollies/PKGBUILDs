# Maintainer: Michał Wojdyła < micwoj9292 at gmail dot com >
# Contributor:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Clint Valentine <valentine.clint@gmail.com>

pkgname=mosdepth
pkgver=0.3.8
pkgrel=1
pkgdesc='Fast BAM/CRAM depth calculation for WGS, exome, or targeted sequencing'
arch=('x86_64')
url="https://github.com/brentp/${pkgname}"
license=('MIT')
makedepends=('git' 'nim' 'nimble' 'htslib')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz"
        "https://patch-diff.githubusercontent.com/raw/brentp/mosdepth/pull/236.patch")
sha256sums=('68d7cb05925985207b48f8cf859e96312226a1fb903ecb2941bc97f25e1643c0'
            '717a7974f5eecd4bead65f130eb5e4489d2050e66d95d26c80dc53e8ed431f3f')

prepare() {
  cd "${pkgname}-${pkgver}"

  patch -p1 -i ../236.patch
}

build() {
  cd "${pkgname}-${pkgver}"
  nimble build -y --passC:-Wno-error=incompatible-pointer-types
}

package() {
  cd "${pkgname}-${pkgver}"

  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
  install -Dm755 "${pkgname}" "${pkgdir}/usr/bin/${pkgname}"
}
