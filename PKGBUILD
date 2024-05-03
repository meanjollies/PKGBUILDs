# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Shaw <puxx@mail.ustc.edu.cn>
# Contributor: Nick <iglu.sitar at gmail dot com>
# Contributor: Angus Gibson <darthshrine@gmail.com>

pkgname=ipbt
pkgver=20240501.bc876ea
pkgrel=1
pkgdesc='A high-tech ttyrec player'
arch=('x86_64')
url="https://www.chiark.greenend.org.uk/~sgtatham/${pkgname}"
license=('MIT')
depends=('ncurses' 'perl')
makedepends=('cmake')
source=("${url}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha256sums=('9bd4ace9028d8932b28981d83be850b2f9ac9ffd27bdeaddd61defca4e2e2762'
            '303ea3d77bdac41a33ec89fd4a10ba86b9a0100a9091dc396d73bee6ff516a26')

prepare() {
  patch -p0 -i ../${pkgname}.patch
}

build() {
  cd "${pkgname}-${pkgver}"

  cmake -DCMAKE_INSTALL_PREFIX=/usr . 
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  install -Dm755 ipbt "${pkgdir}/usr/bin/ipbt"
  install -Dm755 ttydump "${pkgdir}/usr/bin/ttydump"
  install -Dm755 ttygrep "${pkgdir}/usr/bin/ttygrep"
  install -Dm644 ipbt.1 "${pkgdir}/usr/share/man/man1/ipbt.1"
  install -Dm644 LICENCE "${pkgdir}/usr/share/licenses/${pkgname}/LICENCE"
}

