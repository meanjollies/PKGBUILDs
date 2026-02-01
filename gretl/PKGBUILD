# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: quomoow <quomoow@gmail.com>
# Contributor: Thomas Mudrunka <harvie@@email..cz>

pkgname=gretl
pkgver=2026a
pkgrel=1
pkgdesc='A cross-platform software package for econometric analysis, written in the C programming language'
arch=('x86_64')
url='https://gretl.sourceforge.net/'
license=('GPL-3.0-only')
options=('!makeflags')
depends=('gtksourceview3' 'blas' 'curl' 'lapack' 'mpfr' 'fftw' 'gnuplot' 'gmp')
optdepends=('readline: provides a nice editable command line in gretlcli'
            'JSON-GLib: provides for parsing of data from various websites'
            'openmpi: provides means for dividing labor among multiple nodes')
source=("https://downloads.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.xz")
sha256sums=('179695deb91939eda0f5a4010ae854adea783b689da5590056da05ceeabdaf64')

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr --disable-xdg-utils
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
}
