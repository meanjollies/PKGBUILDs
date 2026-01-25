# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=s6
pkgver=2.14.0.1
pkgrel=1
pkgdesc='A small suite of programs for UNIX, designed to allow process supervision'
arch=('x86_64')
url="https://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs' 'execline')
options=('!lto')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('c25afe817cbc3f594efc5050351f8b9101ba78616d0ce915658f370e7ee2e258'
            '9531c0ff811bfb823521db8a6c666d0f52158715206b2a886585a727f5f73ab0')

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
