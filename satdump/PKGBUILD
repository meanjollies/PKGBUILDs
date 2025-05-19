# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=satdump
pkgver=1.2.2
pkgrel=2
pkgdesc='A generic satellite processing software'
arch=('x86_64')
license=('GPL-3.0-only')
url='https://github.com/altillimity/SatDump'
depends=('airspy' 'fftw' 'glfw' 'hackrf' 'jemalloc' 'libad9361' 'libpng' 'libvolk' 'nng' 'ocl-icd' 'portaudio' 'rtl-sdr' 'zenity' 'zstd')
makedepends=('boost' 'cmake' 'opencl-headers')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/${pkgver}.tar.gz"
	"${pkgname}.patch")
optdepends=('limesuite' 'bladerf')
sha256sums=('2ab7c6126e426ad79972b274cc380c0bb04c9e755d746d67f3af92c1dd569209'
            '7656e9c4be11925a27430542a2c35c7c4cd84957969050f337b0cb0473258610')

prepare() {
  patch -p0 -i ../${pkgname}.patch
}

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
