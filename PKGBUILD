# Maintainer: Cameron Banta <cbanta@gmail.com>
pkgname=lua51-pc
pkgver=1.0.0
pkgrel=1
pkgdesc="Lua Process Call"
license=('MIT/X11')
arch=('i686' 'x86_64')
url="http://www.batbytes.com/files"
depends=('lua51')
source=(https://github.com/LuaDist/lpc/tarball/$pkgver)


build() {
	cd $srcdir
	ln -s $(find -name LuaDist-lpc-*) lpc
	cd "$srcdir/lpc"
	make CFLAGS="$CFLAGS -fPIC" LDFLAGS="$LDFLAGS -shared"
}

package() {
	cd "$srcdir/lpc"
	# does not respect DESTDIR
	make install PREFIX="$pkgdir"/usr
}
md5sums=('d25afbbb5feaf6d966306e80dfef11fd')
