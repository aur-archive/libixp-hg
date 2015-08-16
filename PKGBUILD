# Maintainer: N30N <archlinux@alunamation.com>
# Contributor: Anthony Martin <ality@pbrane.org>
# Contributor: rransom <rransom.8774@gmail.com>
# Contributor: Wolf Ramovsky <wolf.ramovsky@gmail.com>
# Contributor: Benjamin van der Burgh <benjaminvdb@gmail.com>

pkgname="libixp-hg"
pkgver=148.b3e7c886af96
pkgrel=2
pkgdesc="The latest hg pull of libixp, a standalone client/server 9p library"
url="http://libs.suckless.org/libixp"
license=("MIT")
arch=("i686" "x86_64")
makedepends=("mercurial" "txt2tags")
provides=("libixp")
options=("staticlibs")
source=("libixp::hg+https://libixp.googlecode.com/hg")
md5sums=("SKIP")

pkgver() {
	cd libixp
	echo "$(hg identify -n).$(hg identify -i)"
}

build() {
	cd libixp
	make
}

package() {
	cd libixp
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim: set noet ff=unix
