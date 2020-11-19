# Maintainer: Sylvain POULAIN <sylvain.poulain@giscan.com>

pkgname=pyfoam
_pkgname=PyFoam
pkgver=2020.5
pkgrel=1
pkgdesc='A python library to control OpenFOAM-runs and manipulate OpenFOAM-data.'
url='http://openfoamwiki.net'
arch=('any')
license=('GPLv2+')
depends=('python-numpy')
source=("$_pkgname-$pkgver.tar.gz::https://files.pythonhosted.org/packages/65/95/0d27b17db10da615c5aa1061ef3bc4b9c60c68c9c6ebed724b40e4d502a2/$_pkgname-$pkgver.tar.gz")
sha512sums=('7fce65af70c6bb21c6be683dfe94fe92b4f4006b753eb41efb4d2ecf521be75c9cd9a5abcbfd79e0c023182a91decf3f96354515fdc10bfd68e3bac4d0f8fd56')

build() {
  cd "$_pkgname-$pkgver"
  python setup.py build
}

check() {
  cd "$_pkgname-$pkgver"
  python setup.py test
}

package() {
  cd "$_pkgname-$pkgver"

  python setup.py install --prefix=/usr --root="$pkgdir" --optimize=1
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/LICENSE.rst"
}
