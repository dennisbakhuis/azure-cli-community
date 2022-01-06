# Maintainer: Dennis Bakhuis <arch-aur@bakhuis.nu>
pkgname=azure-cli-community
pkgver=2.32.0
pkgrel=1
pkgdesc="Azure cloud management installed using virtualenv (conda compatible)"
arch=('x86_64')
url="https://github.com/Azure/azure-cli"
license=('MIT')
depends=('python')
makedepends=('git' 'python-virtualenv')
conflicts=('azure-cli' 'python-azure-cli')
source=('azure-cli-community::git://github.com/dennisbakhuis/azure-cli-community.git')
md5sums=('SKIP')

build() {
	cd "$pkgname"
	virtualenv -p /usr/bin/python venv
  source venv/bin/activate
	python -m pip install azure-cli=="$pkgver"
}

package() {
	cd "$pkgname"
  mkdir -pv "$pkgdir/opt/$pkgname/"
  cp -r * "$pkgdir/opt/$pkgname/"
  mkdir -pv "$pkgdir/usr/bin"
  ln -s "$pkgdir/opt/$pkgname/venv/bin/az" "$pkgdir/usr/bin/az"
}
