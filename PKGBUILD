pkgname=python2-pillow
_appname=Pillow
pkgver=2.1.0
pkgrel=1
pkgdesc="Python Imaging Library (PIL) fork."
arch=(i686 x86_64)
url="https://github.com/python-imaging/Pillow"
license=('BSD')
depends=('python2')
provides=('python2-imaging')
conflicts=('python2-imaging')
makedepends=('python2-distribute')
source=("http://pypi.python.org/packages/source/P/${_appname}/${_appname}-${pkgver}.zip")
md5sums=('ec630d8ae15d4a3c4ae7b7efdeac8200')

package() {
  cd "$srcdir/$_appname-$pkgver"
  python2 setup.py install --root="$pkgdir/" --optimize=1

  # thanks @gosella
  # do not have files ending in .py in /usr/bin
  # also, fix python-pillow conflict
  for f in pildriver pilprint pilconvert pilfile pilfont; do
    mv -v "${pkgdir}"/usr/bin/${f}{.py,2}
  done
}
