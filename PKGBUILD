# Maintainer: Max Pray a.k.a. Synthead <synthead@gmail.com>
# Contributor: Kaos < gianlucaatlas at gmail dot com >
# Contributor: Christoph Zeiler <archNOSPAM_at_moonblade.dot.org>
# Contributor: Matthew Sharpe <matt.sharpe@gmail.com>

pkgname=ophcrack
pkgver=3.5.0
pkgrel=1
pkgdesc="A free Windows password cracker based on rainbow tables"
arch=('i686' 'x86_64')
url=("http://ophcrack.sourceforge.net")
license=('GPL')
depends=('qt4')
optdepends=('qwt: enable graph')
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname/$pkgver/$pkgname-$pkgver.tar.bz2"
        'ophcrack.desktop')
md5sums=('1c61adde21c5dc226515cbd1dc654c60'
         '664599c4fd7fd210e6c421459f60e20d')

build() {
	cd "$srcdir/$pkgname-$pkgver"

	./configure --prefix="/usr" --enable-gui --enable-graph
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"

	make DESTDIR="$pkgdir" install

	install -Dm 644 "$srcdir/ophcrack.desktop" "$pkgdir/usr/share/applications/ophcrack.desktop"
	install -Dm 644 "src/gui/pixmaps/os.xpm" "$pkgdir/usr/share/$pkgname/pixmaps/os.xpm"
}
