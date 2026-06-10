# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

_pkgname=mini
pkgname=cpp-${_pkgname}
pkgver=0.9.20
pkgrel=1
pkgdesc="Tiny, header only C++ library for manipulating INI files."
arch=('any')
license=('MIT')
conflicts=('mini-git')
url="https://github.com/metayeti/mINI"
source=("${_pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
sha256sums=('966c023f04d31f88944fba9c7e6b1c99ad802f3608d2ce8efc645de0fbcaa8c0')

package() {
  cd "mINI-${pkgver}"

  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${_pkgname}/LICENSE"
  install -D -m644 src/mini/ini.h "${pkgdir}/usr/include/mini/ini.h"
}
