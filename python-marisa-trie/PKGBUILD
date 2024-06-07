# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Mark E.A. <evalapply ``dot'' aur ``at'' airmail ``dot'' cc>

pkgname=python-marisa-trie
_pyname=marisa_trie
pkgver=1.2.0
pkgrel=1
pkgdesc='Static memory-efficient & fast Trie-like structures for Python (based on marisa-trie C++ library)'
arch=('any')
url="https://github.com/pytries/marisa-trie"
license=('MIT')
depends=('python')
makedepends=('cython' 'python-pip' 'python-setuptools' 'python-wheel')
source=("https://files.pythonhosted.org/packages/ff/3b/e3b9e08c393acc474e7a60df6f5e180af103ad25b0c29cee3ce2564447eb/${_pyname}-${pkgver}.tar.gz")
sha256sums=('fedfc67497f8aa2757756b5cf493759f245d321fb78914ce125b6d75daa89b5f')

build() {
  cd "${_pyname}-${pkgver}"

  ./update_cpp.sh

  python setup.py build
}

package() {
  cd "${_pyname}-${pkgver}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
