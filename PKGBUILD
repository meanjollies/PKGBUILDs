# Generated by gem2arch (https://github.com/anatol/gem2arch)
# Contributor: Ethan Best <kc9ydn@gmail.com>
# Contributor: Balló György <ballogyor+arch at gmail dot com>

_gemname=gdk3
pkgname=ruby-$_gemname
pkgver=3.0.8
pkgrel=1
pkgdesc='Ruby/GDK3 is a Ruby binding of GDK-3.x.'
arch=(any)
url='http://ruby-gnome2.sourceforge.jp/'
license=(LGPL2.1)
depends=(ruby-cairo-gobject ruby-gdk_pixbuf2 ruby-gobject-introspection ruby-pango)
options=(!emptydirs)
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)
sha1sums=('c336d8ecd0540be1c610ba5e1949baf548229f97')

package() {
  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install -i "$pkgdir/$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
  rm "$pkgdir/$_gemdir/cache/$_gemname-$pkgver.gem"
}
