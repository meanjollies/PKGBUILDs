# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: DavidK <david_king@softhome.net>
# Contributor: Lex Black <autumn-wind@web.de>
# Contributor: Roberto Alsina <ralsina@kde.org>

pkgname=afnix
pkgver=4.0.0
pkgrel=2
pkgdesc='Multi-threaded functional programming language'
arch=('x86_64')
url='http://www.afnix.org'
license=('LicenseRef-AFNIX')
depends=('ncurses' 'gcc-libs')
source=("${url}/ftp/afnix-src-${pkgver}.tgz"
        "gcc16-fixes.patch")
sha256sums=('8b971594990aafab02f7dca3750485142facdfcf00827f6a7ac1409784c9752e'
            'ca92521f39f2486f4d9a63a8eecccb4219ab244a9f6d5fd56aa2946849d35ec1')

prepare() {
  patch -p0 -i ../gcc16-fixes.patch
}

build() {
  cd "${pkgname}-src-${pkgver}"

  ./cnf/bin/afnix-setup -o --prefix="${pkgdir}/usr"
  make
}

package() {
  cd "${pkgname}-src-${pkgver}"

  make install
  install -d "${pkgdir}/usr/share/emacs/site-lisp"
  install etc/unx/*.el -t "${pkgdir}/usr/share/emacs/site-lisp"
  install -D doc/xml/eul/std-us-legal.xml "${pkgdir}/usr/share/licenses/afnix/LICENSE"
}
