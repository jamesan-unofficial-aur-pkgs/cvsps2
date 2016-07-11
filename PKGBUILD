# Maintainer: Alastair Stuart <alastair@muto.so>

pkgname=cvsps2
_pkgname=${pkgname%2}
pkgver=2.2b1
pkgrel=1
pkgdesc="cvsps v2, needed by 'git cvsimport'"
arch=('i686' 'x86_64')
url="http://cvsps.sourceforge.net"
license=('GPL')
provides=("$_pkgname=$pkgver")
conflicts=("$_pkgname")
source=("https://downloads.sourceforge.net/project/$_pkgname/$_pkgname-$pkgver.tar.gz"
        "inet_addr-64bit.patch")
md5sums=('997580e8e283034995b9209076858c68'
         '669d2eefca07ef46cafbe3686d616239')

prepare() {
  cd "$_pkgname-$pkgver"

  patch -p1 < ../inet_addr-64bit.patch
}
build() {
  cd "$_pkgname-$pkgver"

  make
}

package() {
  cd "$_pkgname-$pkgver"

  make prefix="$pkgdir/usr" install
}
