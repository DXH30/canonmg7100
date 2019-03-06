pkgname=canon-pisma-mg7100-complete
pkgver=4.40
pkgrel=1
pkgdesc="Stand alone driver for Canon MG7100"
url='https://support-asia.canon-asia.com/contents/ASIA/EN/0100551202.html'
arch=('i686' 'x86_64')
license=('custom')
install="${pkgname}.install"
depends_x86_64=('lib32-popt' 'lib32-libpng12' 'lib32-libusb-compat' 'lib32-libtiff4' 'lib32-libxml2' 'lib32-gtk2')  
depends_i686=('popt' 'libpng12' 'libusb-compat' 'libtiff4' 'libxml2' 'gtk2')

makedepends=('deb2targz' 'sed')

source=('http://gdlp01.c-wss.com/gds/2/0100005512/01/cnijfilter-mg7100series-4.00-1-deb.tar.gz'
	"${pkgname}.license"
	"${pkgname}-scangear.desktop"
	"${pkgname}-scangear-icon.png")
md5sums=('83bc4c91e968edb2377767ae049d6741'
'3740a3fd691fdbebcdf00c78998d6b93'
'b1a14b08936ee9fd65e0ec2ff884a5a6'
'3feefd413092d7152f47b7451ba79efe')
_series=7100
_printDrvSrc='cnijfilter-mg7100series-4.00-1-deb'

_printDrvDebCommon='cnijfilter-common_4.00-1_i386'
_printDrvDebMain='cnijfilter-mg7100series_4.00-1_i386'

_printDrvDebCommon64='cnijfilter-common_45.00-1_amd64'
_printDrvDebmain64='cnijfilter-mg7100series_4.00-1_amd64'

_ppdFile="canonmg${_series}.ppd"

build(){
	cd ${srcdir}

	tar zxf cnijfilter-mg${_series}-4.00-1-deb.tar.gz
}

package() {
	cd ${pkgdir}

	cp "${srcdir}/${_printDrvSrc}/packages/${_printDrvDebCommon}.deb" .
	cp "${srcdir}/${_printDrvSrc}/packages/${_printDrvDebMain}.deb" .

	deb2targz "${_printDrvDebCommon}.deb"
	deb2targz "${_printDevDebMain}.deb"
	deb2targz "${_printDevDebCommon64}.deb"
	deb2targz "${_prinDevDebMain64}.deb"

	rm -v *.deb
	install -vDm 644 "${Srcdir}/${pkgname}.license" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
