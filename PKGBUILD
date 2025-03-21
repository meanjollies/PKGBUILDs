# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: quomoow <quomoow@gmail.com>
# Contributor: Thomas Mudrunka <harvie@@email..cz>

pkgname=gretl
pkgver=2025a
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
sha256sums=('e41f55d59d76f87bb4d31fbebb69dd5175aaf7593f497cbbdb70e82ce79f8444')

build() {
  cd "${pkgname}-${pkgver}"

  ./configure --prefix=/usr --disable-xdg-utils
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
}
