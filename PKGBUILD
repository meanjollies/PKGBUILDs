# Maintainer:  Andrew O'Neill <andrew at haunted dot sh>
# Contributor: Mark E.A. <evalapply ``dot'' aur ``at'' airmail ``dot'' cc>

pkgname=python-marisa-trie
_pyname=marisa_trie
pkgver=1.4.1
pkgrel=1
pkgdesc='Static memory-efficient & fast Trie-like structures for Python (based on marisa-trie C++ library)'
arch=('any')
url="https://github.com/pytries/marisa-trie"
license=('MIT')
depends=('python')
makedepends=('cython' 'python-pip' 'python-setuptools' 'python-wheel')
source=("https://files.pythonhosted.org/packages/77/5d/e235921b5b74818cb65b557fa05cc6201c2c1612d4866ff75c835bcf808d/${_pyname}-${pkgver}.tar.gz")
sha256sums=('44ce3bdbeb7c950d463e460184fc3e18702df9ef0edb826bac672fd789fb1d20')

build() {
  cd "${_pyname}-${pkgver}"

  python setup.py build
}

package() {
  cd "${_pyname}-${pkgver}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
