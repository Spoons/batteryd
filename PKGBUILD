# Maintainer: Michael Ciociola <childofunix@gmail.com>
pkgname=batteryd
pkgver=1.0.0
pkgrel=1
pkgdesc="Battery Notification Daemon"
arch=("any")
license=('GPL')
depends=("python")
makedepends=("git")
source=("batteryd")
md5sums=("SKIP")

package() {
	cd "$srcdir"
	install -Dm 755 batteryd -t "$pkgdir/usr/bin/"
	install -Dm 644 batteryd.service -t "$pkgdir/usr/lib/systemd/user"
}
