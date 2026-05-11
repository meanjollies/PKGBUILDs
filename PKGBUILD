# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Josh VanderLinden <arch@cloudlery.com>

pkgname=s6
pkgver=2.15.0.0
pkgrel=1
pkgdesc='A small suite of programs for UNIX, designed to allow process supervision'
arch=('x86_64')
url="https://skarnet.org/software/${pkgname}"
license=('ISC')
depends=('skalibs' 'execline')
options=('!lto')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('27dff73d626285540133e075e75887087f5117fd51de59503ef7d29e96f69e4c'
            'd20e28dbf9ac33e1b815659a212e6cfca7d392d55ae9758b257ad4ed0627e460')

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
