# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=satdump
pkgver=1.2.0
pkgrel=1
pkgdesc='A generic satellite processing software'
arch=('x86_64')
license=('GPL-3.0-only')
conflicts=('satdump-git')
url='https://github.com/altillimity/SatDump'
depends=('airspy' 'fftw' 'glfw' 'hackrf' 'jemalloc' 'libad9361' 'libpng' 'libvolk' 'nng' 'ocl-icd' 'portaudio' 'rtl-sdr' 'zstd')
makedepends=('boost' 'cmake' 'opencl-headers')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz")
optdepends=('limesuite' 'bladerf')
sha256sums=('099d51864a0a3e374b0d12a9ad13d8ac263b9ab0cb88d4e5b08c2b72b9afb20e')

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
