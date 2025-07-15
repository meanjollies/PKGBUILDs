# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Kevin Slagle <kjslag at gmail dot com>

pkgname=regina-normal
pkgver=7.3.1
pkgrel=1
pkgdesc='Software for low-dimensional topology'
arch=('x86_64')
url='https://regina-normal.github.io'
license=('GPL-2.0-or-later')
depends=('gmp' 'graphviz' 'jansson' 'libxml2' 'popt' 'python3' 'qt6-base' 'qt6-svg' 'tokyocabinet' 'zlib')
makedepends=('cmake')
optdepends=('doxygen: Generate C++/Python API docs'
	    'cppunit: Build full test suite'
            'libxslt: Generate the user handbook')
source=("https://github.com/${pkgname}/regina/archive/regina-${pkgver}.tar.gz")
sha256sums=('367f6307054ba1cd612abf23955a07d02bc081865145476d3ad2d2e36d633880')

prepare() {
  cd "regina-regina-${pkgver}"

  sed -i 's/unsigned svgLen/size_t svgLen/' qtui/src/packets/linkgraph.cpp qtui/src/packets/facetgraphtab.cpp
}

build() {
  local cmake_options=(
    -B build
    -S "regina-regina-${pkgver}"
    -W no-dev
    -D CMAKE_BUILD_TYPE=Release
    -D CMAKE_INSTALL_PREFIX=/usr
  )

  cmake "${cmake_options[@]}"
  cmake --build build
}

package() {
  DESTDIR="${pkgdir}" cmake --install build
}
