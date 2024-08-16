# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

_pkgname=mini
pkgname=cpp-${_pkgname}
pkgver=0.9.16
pkgrel=1
pkgdesc="Tiny, header only C++ library for manipulating INI files."
arch=('any')
license=('MIT')
conflicts=('mini-git')
url="https://github.com/metayeti/mINI"
source=("${_pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
sha256sums=('ce20e12b1e3bcd79d6eaa47bf8d4bb319e843dfa3585e069e73d581bdf0a81ec')

package() {
  cd "mINI-${pkgver}"

  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE"
  install -D -m644 src/mini/ini.h "${pkgdir}/usr/include/mini/ini.h"
}
