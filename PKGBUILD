# Maintainer: Mequam <blue9ja@gmail.com>
pkgname="infinisim"
pkgver=1.0
pkgrel=0
pkgdesc="local symulator for developing on the infiniwatch"
arch=("x86_64")
url="https://github.com/InfiniTimeOrg/InfiniSim"
makedepends=(cmake sdl2 gcc npm libpng)
#source=("$pkgname-$pkgver::git+https://github.com/InfiniTimeOrg/InfiniSim.git")
#md5sums=("SKIP")
#license=('UNKOWIN')
#groups=()
#depends=()
#checkdepends=()
#optdepends=()
#provides=()
#conflicts=()
#replaces=()
#backup=()
#options=()
#install=
#changelog=

#noextract=()
#validpgpkeys=()

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
