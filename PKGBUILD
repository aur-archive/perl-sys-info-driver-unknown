# Maintainer: Jason St. John <jstjohn .. purdue . edu>

_perlmod=Sys-Info-Driver-Unknown
_modnamespace=Sys
pkgname=perl-sys-info-driver-unknown
pkgver=0.78
pkgrel=3
pkgdesc="Sys::Info::Driver::Unknown - Compatibility layer for Sys::Info"
arch=('i686' 'x86_64')
url="http://search.cpan.org/dist/${_perlmod}"
license=('GPL' 'PerlArtistic')
depends=('perl-sys-info-base>=0.7803')
makedepends=('perl-test-sys-info>=0.20')
options=('!emptydirs')
source=("http://cpan.org/modules/by-module/${_modnamespace}/${_perlmod}-${pkgver}.tar.gz")
sha512sums=('375777dc6da5d19412041e7dae2ed141f3a0abaa8abcc2eae6fbddc0a7fab951628763225c95782ec11fc244b331aea9524ebe71e5edad3fb2f581c74c29da44')

build() {
	cd "${_perlmod}-${pkgver}"

	# Install module in vendor directories.
	PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
	make
}

check() {
	cd "${_perlmod}-${pkgver}"
	make test
}

package() {
	cd "${_perlmod}-${pkgver}"
	make install DESTDIR="${pkgdir}"
}
