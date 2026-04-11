# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Konstantin Gizdov <arch at kge dot pw>
# Contributor: banbanchs <memory.silentvoyage@gmail.com>

pkgname=libck
pkgver=0.7.2
pkgrel=2
pkgdesc='A concurrency primitives, safe memory reclamation mechanisms C library'
arch=('x86_64')
url='http://concurrencykit.org'
license=('BSD-2-Clause' 'Apache-2.0')
depends=('glibc')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/concurrencykit/ck/archive/${pkgver}.tar.gz")
sha256sums=('568ebe0bc1988a23843fce6426602e555b7840bf6714edcdf0ed530214977f1b')

build() {
  cd "${srcdir}/ck-${pkgver}"

  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/ck-${pkgver}"

  make DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
