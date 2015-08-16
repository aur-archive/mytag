# Contributer: giacomogiorgianni@gmail.com 

pkgname=mytag
pkgver=1.2
rel=20121114
pkgrel=1
pkgdesc="An tagtool doesn't cut it and neither does any other music tagging program GTK3 ID3v2.4 compatible."
arch=('i686' 'x86_64')
url="https://opendesktop.org/content/show.php/mytag%3A+Python+music+tagger+and+organiser?content=155321"
license=('GPL')
#install=$pkgname.install
makedepends=('automoc4' 'cmake')
depends=('python2-eyed3' 'python2>=2.7' 'gnome-icon-theme')
options=(!strip)
#source=(https://github.com/downloads/lachlan-00/mytag/${pkgname}-${pkgver}.tar.gz)
source=(https://opendesktop.org/CONTENT/content-files/155321-${pkgname}-${pkgver}.tar.gz)
md5sums=('9353f301d83ee2f7cb55f0707281b107')

build() {
  cd ${srcdir}/${pkgname}
  sed -i -e "s=/usr/bin/env python=/usr/bin/env python2=g" mytag/mytag.py
  sed 2a"INSTALL_ROOT="$pkgdir -i Makefile
  mkdir -p "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications" "${pkgdir}/usr/share/pixmaps"
  sed -i -e "12s|/usr/bin|'$pkgdir/usr/bin'|" Makefile
  sed -i -e "13s|/usr/share/pixmaps|'$pkgdir/usr/share/pixmaps'|" Makefile
  sed -i -e "14s|/usr/share/applications|'$pkgdir/usr/share/applications'|" Makefile
  make INSTALLPATH="$pkgdir/usr/share/mytag" INSTALL_ROOT="$pkgdir" install
  
}


