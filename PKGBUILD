pkgname=arm-complier
pkgver=5.06u7
pkgrel=1
pkgdesc="Arm Complier 5."
arch=('x86_64')
license=('custom')
makedepends=('zip')
depends=('arm-development-studio')
source=(
	"DS500-PA-00003-r5p0-26rel0.tgz"
	"patcher"
)

prepare() {
    cd "${srcdir}"
}

package() {
	#install
	cd "DS500-PA-00003-r5p0-26rel0/Installer/"
	./setup.sh --i-agree-to-the-contained-eula -f -d "${pkgdir}/usr/local/ARM_Compiler_${pkgver}"
    cd ../..

	#fix
	rm -f "${pkgdir}/usr/local/ARM_Compiler_${pkgver}/install_history"

	#patch
	bash -c "./patcher --dir "${pkgdir}/usr/local/ARM_Compiler_${pkgver}/" --nomusic;true"
}
sha256sums=('14a57a13626f3cf82298d9d0d0964c9542a821d2b17788116ee6479a7a4eb557'
            '71ba199c5005deb8372be4f9be07b3d94ccbdda3973e25d029ef464de051ddf2')
