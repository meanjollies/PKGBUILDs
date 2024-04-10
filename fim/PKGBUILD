# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Steven Honeyman <stevenhoneyman at gmail com>
# Contributor: Alexej Magura <agm2819*gmail*>
# Contributor: Dragonlord <dragonlord[at]seznam[.]cz>
# Contributor: daniel <quite a hack org>

pkgname=fim
pkgver=0.7.0
pkgrel=1
pkgdesc='FIM (Fbi IMproved) is a highly customizable and scriptable image viewer.'
arch=('i686' 'x86_64')
url='https://www.nongnu.org/fbi-improved/'
license=('GPL-2.0-or-later')
depends=('libexif' 'terminus-font')
optdepends=('aalib: ASCII art support'
            'djvulibre: djvu support'
            'giflib: GIF support'
            'imagemagick: use convert for unrecognized files'
            'libjpeg-turbo: JPEG support'
            'libpng: PNG support'
            'libspectre: postscript support'
            'libtiff: TIFF support'
            'sdl: X support')
source=("http://download.savannah.gnu.org/releases/fbi-improved/${pkgname}-${pkgver}.tar.gz")
sha256sums=('44cf99e37ff93a219734fb379128a7714c4a8e689f06338c7e479dc949ad53ff')

build() {
  cd "${pkgname}-${pkgver}"

  PKG_CONFIG=/usr/bin/pkg-config ./configure \
    LIBS=-lpthread --prefix=/usr --disable-debug \
    --enable-hardcoded-font --disable-avif --disable-webp

  make
}

package() {
  cd "${pkgname}-${pkgver}"

  make DESTDIR=${pkgdir} install
}
