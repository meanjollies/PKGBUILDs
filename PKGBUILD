# Maintainer: Konstantin Gizdov <arch at kge dot pw>
# Contributor: Axel Gembe <derago@gmail.com>
# Contributor: Oleksandr Natalenko <oleksandr@natalenko.name>
# Contributor: Antoine Lubineau <antoine@lubignon.info>

pkgname=dnsperf
pkgver=2.14.0
pkgrel=1
pkgdesc="Tools that measure performance of authoritative Domain Name services"
arch=('x86_64')
url="https://www.dns-oarc.net/tools/dnsperf"
license=('Apache-2.0')
depends=('ldns' 'libck' 'libnghttp2')
source=("https://www.dns-oarc.net/files/${pkgname}/${pkgname}-${pkgver}.tar.gz")
b2sums=('308b11902f35e0f6a84cdd2204cc37a07603cf7a6d41f7eae865ee72dca8cf1b52ff5969ed8747c5229befcbe60556622188ed8cb7acce41e71ac93b85b5b197')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr --mandir=/usr/share/man
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
