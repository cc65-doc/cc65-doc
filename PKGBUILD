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
    cd "$srcdir/$pkgname"
    for mp in *.1; do
        cp "$mp" "$pkgdir/usr/share/man/man1/$mp"
    done

    # copy license to fakeroot
    cp LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

    # clean up VCS stuff
    cd ../..
    rm -rf "$srcdir" "$pkgname"
}
