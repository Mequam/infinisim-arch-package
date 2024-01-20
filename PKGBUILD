# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname="infinisim"
pkgver=1.0
pkgrel=0
pkgdesc="local symulator for developing on the infiniwatch"
arch=("x86_64")
url="https://github.com/InfiniTimeOrg/InfiniSim.git"

#license=('GPL')
#groups=()
#depends=()
makedepends=(cmake sdl2 gcc npm libpng)
#checkdepends=()
#optdepends=()
#provides=()
#conflicts=()
#replaces=()
#backup=()
#options=()
#install=
#changelog=

source=("$pkgname-$pkgver::git+https://github.com/InfiniTimeOrg/InfiniSim.git")
noextract=()
md5sums=("SKIP")
validpgpkeys=()

git_url="https://github.com/InfiniTimeOrg/InfiniSim.git"

prepare() {
	cd "${srcdir}"
	if [ ! -d "InfiniSim" ]; then
		echo "[prepare] retrieving source!"
		git clone --recursive --depth=1 $git_url
		cd "InfiniSim"
		npm install lv_font_conv@1.5.2
	else
		echo "[prepare] source already downloaded!"
	fi
}

build() {
	cd "${srcdir}/InfiniSim"
	cmake -S . -B build
	cmake --build build -j4
}

check() {
	cd "$pkgname-$pkgver"
	#make -k check
}

package() {
	echo "${pkgdir}"
	echo "${srcdir}"
	mkdir -p "${pkgdir}/usr/bin"
	cp "${srcdir}/InfiniSim/build/infinisim" "${pkgdir}/usr/bin/"
}
