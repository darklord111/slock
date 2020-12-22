# Maintainer:

pkgname=slock-aseem
_pkgname=slock
pkgver=0.8.2.r1062.2087ab9
pkgrel=1
epoch=1
pkgdesc="My build of slock."
url='https://github.com/mistersmee/slock'
arch=(any)
license=('MIT')
depends=('git')
makedepends=('make')
source=('git://github.com/mistersmee/slock')
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${_pkgname}"
	printf "%s.r%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" \
		"$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/${_pkgname}
}

build() {
	cd "${_pkgname}"
	make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
	cd "${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
}
