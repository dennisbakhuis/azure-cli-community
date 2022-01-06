# Maintainer: Dennis Bakhuis <arch-aur@bakhuis.nu>
pkgname=azure-cli-community
pkgver=2.32.0
pkgrel=1
pkgdesc="Tool to manage your Azure cloud (system-wide virtualenv install)"
arch=('x86_64')
url="https://github.com/Azure/azure-cli"
license=('MIT')
depends=('python')
makedepends=('python-pip' 'python-virtualenv')
conflicts=('azure-cli' 'python-azure-cli')
md5sums=('SKIP')

build() {
	cd "$pkgname"
	virtualenv -p /usr/bin/python venv
  source venv/bin/activate
	pip install azure-cli=="$pkgver"
}

package() {
	cd "$pkgname"
  cp -r * "$pkgdir/opt/$pkgname/"
  ln -s "$pkgdir/opt/$pkgname/venv/bin/az" "$pkgdir/bin/az"
}
