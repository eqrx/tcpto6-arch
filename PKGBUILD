# Maintainer: Alexander Sowitzki <dev@eqrx.net>
pkgname=tcpto6
pkgdesc='Listen on a TCP addr and forward connections to a TCPv6 listener'
pkgver=0.0.6
pkgrel=1
arch=('x86_64' 'aarch64')
url="https://dev.eqrx.net/$pkgname"
license=('AGPL3')
makedepends=('go')
source=("$pkgname-$pkgver.tar.gz::https://github.com/eqrx/$pkgname/archive/refs/tags/v$pkgver.tar.gz")
sha512sums=('ba56da5fd146799033846eea3bfba8d38ef1e72195f75250972b6ea0f83688053ae325c3ff8f7fbbc10468bd1d035b16f7bb843052c77b80f7046a6cbbaad34e')

build() {
  cd "$pkgname-$pkgver"
  ./build.sh
}

package() {
  cd "$pkgname-$pkgver"
  install -Dm755 init/$pkgname@.service "$pkgdir"/usr/lib/systemd/system/$pkgname@.service
  install -Dm755 bin/$pkgname "$pkgdir"/usr/bin/$pkgname
}
