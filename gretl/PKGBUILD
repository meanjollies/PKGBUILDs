# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: quomoow <quomoow@gmail.com>
# Contributor: Thomas Mudrunka <harvie@@email..cz>

pkgname=gretl
pkgver=2024d
pkgrel=1
pkgdesc='A cross-platform software package for econometric analysis, written in the C programming language'
arch=('x86_64')
url='http://gretl.sourceforge.net/'
license=('GPL-3.0-only')
options=('!makeflags')
depends=('gtksourceview3' 'blas' 'curl' 'lapack' 'mpfr' 'fftw' 'gnuplot' 'gmp')
optdepends=('readline: provides a nice editable command line in gretlcli'
            'JSON-GLib: provides for parsing of data from various websites'
            'openmpi: provides means for dividing labor among multiple nodes')
source=("https://downloads.sourceforge.net/project/${pkgname}/${pkgname}/${pkgver}/${pkgname}-${pkgver}.tar.xz")
sha256sums=('9903568c273db09b6931bc2077408d8c08b2bda4e783a0ea5b2cbc59b5b5dbac')

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr --disable-xdg-utils
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
}
