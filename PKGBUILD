# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname="InfiniSim"
pkgver=1.0
pkgrel=0
pkgdesc="local symulator for developing on the infiniwatch"
arch=("x86_64")
url="https://github.com/InfiniTimeOrg/InfiniSim.git"

#license=('GPL')
#groups=()
#depends=()
#makedepends=()
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

prepare() {
	cd "$pkgname-$pkgver"
	##patch -p1 -i "$srcdir/$pkgname-$pkgver.patch"
	#git clone --recursive --depth=1 $url
}

build() {
	cd "$pkgname-$pkgver"
	#./configure --prefix=/usr
	#make
}

check() {
	cd "$pkgname-$pkgver"
	#make -k check
}

package() {
	cd "$pkgname-$pkgver"
	#make DESTDIR="$pkgdir/" install
}
