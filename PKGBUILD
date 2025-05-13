# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Pablo Lezaeta <prflr88@gmail.com>

pkgname=yash
pkgver=2.59
pkgrel=1
pkgdesc='Yet Another SHell is a POSIX-compliant command line shell'
arch=('i686' 'x86_64' 'armv7h' 'aarch64')
url='https://magicant.github.io/yash/'
license=('GPL-2.0-only')
depends=('ncurses')
makedepends=('asciidoc' 'ed')
options=('lto')
install="${pkgname}.install"
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/magicant/${pkgname}/archive/refs/tags/${pkgver}.tar.gz"
        "${pkgname}.install")
sha256sums=('efe9d299a14d103d259b8a709fa2b664d8ff6ee498523f797f31f67db62e11af'
            'c66c7a4b9da4416082ea57bbec0ce0c2bbc13af340ceb1241b4a4897d8944531')

build() {
  cd "${pkgname}-${pkgver}"

  ./configure \
    --prefix=/usr \
    --enable-array \
    --enable-dirstack \
    --enable-double-bracket \
    --enable-help \
    --enable-history \
    --enable-lineedit \
    --enable-nls \
    --enable-printf \
    --enable-socket \
    --enable-test \
    --enable-ulimit

  make
}

check() {
  cd "${pkgname}-${pkgver}"

  make check
}

package() {
  cd "${pkgname}-${pkgver}"

  make install DESTDIR="${pkgdir}"
  install -Dm0644 doc/*.{css,html} -t "${pkgdir}/usr/share/doc/${pkgname}/"
  install -Dm0644 doc/ja/*.{css,html} -t "${pkgdir}/usr/share/doc/${pkgname}/ja/"
}
