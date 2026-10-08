# Maintainer: kancko <kancko>

pkgname=gnome-rounded-blur
pkgver=1.0.1
pkgrel=1
pkgdesc="GNOME Shell BlurEffect with rounded corners"
arch=('x86_64')
url="https://github.com/kancko/gnome-rounded-blur"
license=('GPL-3.0')
makedepends=(
  'git'
  'meson'
  'mutter'
  'glib2-devel'
  'gobject-introspection'
)
source=("git+https://github.com/darojatun/gnome-rounded-blur.git")
sha256sums=('SKIP')

prepare() {
  cd $pkgname
  git switch gnome51
  meson setup build
}

build() {
  arch-meson $pkgname build
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"
}
