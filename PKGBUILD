pkgname=sharutils
pkgver=4.15.2
pkgrel=3
pkgdesc='Makes so-called shell archives out of many files'
url='https://www.gnu.org/software/sharutils/'
license=('GPL')
arch=('x86_64')
depends=('perl' 'gettext' 'texinfo')
validpgpkeys=('1F967B15DEB2349CACDF3D71D9204CB5BFBF0221')
source=("https://ftp.gnu.org/gnu/${pkgname}/${pkgname}-${pkgver}.tar.xz")
sha256sums=('2b05cff7de5d7b646dc1669bc36c35fdac02ac6ae4b6c19cb3340d87ec553a9a')

prepare() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	sed 's/FUNC_FFLUSH_STDIN/-1/g' -i lib/fseeko.c
}

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	./configure \
		--prefix=/usr \
		--mandir=/usr/share/man \
		--infodir=/usr/share/info \

	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}" install
}
