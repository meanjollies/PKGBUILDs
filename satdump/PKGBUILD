# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=satdump
pkgver=1.2.2
pkgrel=1
pkgdesc='A generic satellite processing software'
arch=('x86_64')
license=('GPL-3.0-only')
url='https://github.com/altillimity/SatDump'
depends=('airspy' 'fftw' 'glfw' 'hackrf' 'jemalloc' 'libad9361' 'libpng' 'libvolk' 'nng' 'ocl-icd' 'portaudio' 'rtl-sdr' 'zstd')
makedepends=('boost' 'cmake' 'opencl-headers')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
optdepends=('limesuite' 'bladerf')
sha256sums=('2ab7c6126e426ad79972b274cc380c0bb04c9e755d746d67f3af92c1dd569209')

build() {
  cd "SatDump-${pkgver}"

  mkdir build
  cd build
  cmake -DCMAKE_BUILD_TYPE=Release ..
  make
}

package() {
  cd "SatDump-${pkgver}/build"

  make DESTDIR="${pkgdir}" install
}
