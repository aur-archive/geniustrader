# Maintainer: perlawk

pkgname=geniustrader
pkgver=svn
pkgrel=2
pkgdesc="GeniusTrader aims to be a full featured toolbox to create trading systems."
arch=('i686' 'x86_64')
url="http://geniustrader.org/"
license=('GPL')
options=()
depends=(svn perl perl-date-calc perl-date-manip)
makedepends=()
install=$pkgname.install
source=( options )
md5sums=( '7dbb6136a54e731138196a2b9e016464')

build() {
  cd "$srcdir/"
}

package() {
  mkdir -p "$pkgdir/usr/share/$pkgname"
  mkdir -p "$pkgdir/usr/share/perl5/vendor_perl/"
  cd "$srcdir"
	svn checkout https://geniustrader.svn.sourceforge.net/svnroot/geniustrader/trunk/Scripts geniustrader/Scripts
  svn checkout https://geniustrader.svn.sourceforge.net/svnroot/geniustrader/trunk/GT geniustrader/GT	
	svn checkout https://geniustrader.svn.sourceforge.net/svnroot/geniustrader/trunk/Windows_Installer/data geniustrader/data	
	rm -rf geniustrader/Scripts/.svn
	rm -rf geniustrader/GT/.svn
	rm -rf geniustrader/data/.svn
  cp -a $pkgname  $pkgdir/usr/share/
  cp $srcdir/options $pkgdir/usr/share/$pkgname/
  cd $pkgdir/usr/share/perl5/vendor_perl
  ln -s ../../$pkgname/GT 
}
