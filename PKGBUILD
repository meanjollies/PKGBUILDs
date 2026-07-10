# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Christopher Vittal ("viralstitch") <chris@vittal.dev>

pkgname=htslib
pkgver=1.24
pkgrel=1
pkgdesc='A C library for high-throughput sequencing data formats'
arch=('x86_64')
url="https://github.com/samtools/${pkgname}"
license=('MIT')
depends=('curl' 'zlib' 'openssl')
provides=('tabix')
replaces=('tabix')
conflicts=('tabix')
options=('staticlibs')
source=("${pkgname}-${pkgver}.tar.bz2::${url}/releases/download/${pkgver}/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('28a8de191381c7a97a35675ceac76fa1ea95e7b678d6a2e9d600a7874e4077de')

build() {
  cd "${pkgname}-${pkgver}"

  CFLAGS+=" -ffat-lto-objects" ./configure \
    --prefix=/usr \
    --enable-libcurl \
    --enable-plugins \
    --with-plugin-dir=/usr/lib/htslib/plugins

  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR=${pkgdir} install

  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"

  # htslib shared library comes installed as 0644
  chmod +x ${pkgdir}/usr/lib/libhts.so.*.*
}
