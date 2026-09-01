# Maintainer: Jan Motulla <github@mergedcloud.de>

pkgname="idea"
pkgver=0.2.1
pkgrel=1
arch=('x86_64')
license=('GPL-3.0-only')
source=("$pkgname-$pkgver.tar.gz::https://github.com/mergedeyes/idea/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('eccd2bb972e499261a8040bd69580c74fa45c4972f8b0f28a69b997be11e5995')
pkgdesc="Tiny CLI for capturing ideas by topic, stored as local JSON"
url="https://github.com/mergedeyes/idea"

makedepends=('cargo')
depends=('glibc' 'gcc-libs')

build(){
	cd "$srcdir/$pkgname-$pkgver"

	cargo build --release --locked
}

package(){
	cd "$srcdir/$pkgname-$pkgver"

	install -Dm755 "target/release/idea" "$pkgdir/usr/bin/idea"

	install -Dm644 "README.md" "$pkgdir/usr/share/doc/${pkgname}/README.md"
	install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
}
