# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

pkgname=oci-cli
pkgver=3.64.0
pkgrel=1
pkgdesc='Command line interface for Oracle Cloud Infrastructure'
arch=('x86_64')
url="https://github.com/oracle/${pkgname}"
license=('Apache-2.0 OR UPL-1.0')
depends=('python' 'python-oci' 'python-arrow' 'python-certifi' 'python-click' 'python-dateutil' 'python-cryptography' 'python-pyopenssl' 'python-jmespath' 'python-terminaltables3' 'python-idna' 'python-prompt_toolkit' 'python-pytz' 'python-six' 'python-retrying' 'python-wcwidth' 'python-yaml')
makedepends=('python-setuptools')
optdepends=('python-cx-oracle: Used by the database service')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/v${pkgver}.tar.gz")
sha256sums=('72266ff00db6089ee9c0443737f36059ad933cc1f328899d811f4ac1a18ddfb4')

prepare() {
  cd "${pkgname}-${pkgver}"

  sed -i -r "s/(==|>|<).*[0-9].*'/'/g" setup.py
  sed -i "s/terminaltables/terminaltables3/g" setup.py src/oci_cli/cli_util.py src/oci_cli/formatting.py
}

build() {
  cd "${pkgname}-${pkgver}"

  python setup.py build
}

package() {
  cd "${pkgname}-${pkgver}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
  install -Dm644 LICENSE.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
