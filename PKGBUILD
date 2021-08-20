# Maintainer: Jake Grossman <jake.r.grossman@gmail.com>
pkgname=cc65-doc-git
pkgver=0.1.0
pkgrel=1
pkgdesc="Documentation for the cc65 c-compiler and associated tools."
url="https://www.github.com/cc65-doc/cc65-doc"
arch=('any')
license=('zlib')
makedepends=('git')
source=("$pkgname::git+$url")
md5sums=('SKIP')

package() {
    # setup fakeroot
    mkdir -p "$pkgdir/usr/share/man/man1"
    mkdir -p "$pkgdir/usr/share/licenses/$pkgname"

    # copy man pages to fakeroot
    cp *.1 "$srcdir/$pkgname/$pkgdir/usr/share/man/man1/."

    # copy license to fakeroot
    cp LICENSE "$srcdir/$pkgname/$pkgdir/usr/share/licenses/$pkgname/."

    # clean up VCS stuff
    rm -rf "$srcdir" "$pkgname"
}
