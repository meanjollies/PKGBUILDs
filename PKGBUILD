# Maintainer: Andrew O'Neill <andrew at haunted dot sh>

_gemname=event_stream_parser
pkgname=ruby-${_gemname}
pkgver=1.0.0
pkgrel=1
pkgdesc='Ruby gem for a lightweight, fully spec-compliant parser for the event stream format'
arch=('x86_64')
url="https://github.com/Shopify/${_gemname}"
license=('MIT')
depends=('ruby' 'rubygems')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('4bc703ac7eb778de92ad5d933f15f5e87bd76b93538ccff5735877b4a383d495')

build() {
  cd "${_gemname}-${pkgver}"

  gem build ${_gemname}.gemspec
}

package() {
  cd "${_gemname}-${pkgver}"

  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install -i "${pkgdir}/${_gemdir}" -n "${pkgdir}/usr/bin" ${_gemname}-${pkgver}.gem
  rm "${pkgdir}/${_gemdir}/cache/${_gemname}-${pkgver}.gem"
  install -Dm644 LICENSE.md "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
