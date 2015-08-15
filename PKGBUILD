# Contributor: Vlatko Kosturjak <kost@linux.hr>

pkgname=gsa
pkgver=3.0.3
pkgrel=1
pkgdesc="Greenbone Security Assistant (gsa) - OpenVAS web frontend"
url="http://www.openvas.org/"
license=GPL
depends=('glibc' 'libmicrohttpd' 'libxml2' 'glib2' 'libxslt' 'gnutls' 'openvas-libraries')
makedepends=('gcc' 'automake' 'cmake' 'doxygen')
conflicts=()
replaces=()
backup=(etc/openvas/gsad_log.conf)
options=('!buildflags')
install=
source=(http://wald.intevation.org/frs/download.php/1158/greenbone-security-assistant-$pkgver.tar.gz gsa-no-werror-remove.patch)
md5sums=('634729feb32c1d9601543ad713e9ab9f' '8a564ebe827c07ac8c1b9d1f4eab9eee')
arch=('i686' 'x86_64')


build() {
  cd $startdir/src/greenbone-security-assistant-$pkgver/
  patch -p1 < $startdir/src/gsa-no-werror-remove.patch
  cmake -DCMAKE_INSTALL_PREFIX=/usr -DSYSCONFDIR=/etc -DLOCALSTATEDIR=/var .
  make
  make DESTDIR="$pkgdir/" install
}
