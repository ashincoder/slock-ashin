# Maintainer: Ashin Antony <ashinant15@gmail.com>

pkgname=slock-ashin-git
pkgver=20170325.35633d4.r6.fba458b
pkgrel=1
pkgdesc='A suckless locker customized in my own way with .'
arch=(x86_64)
url='https://github.com/ashincoder/slock-ashin.git'
license=('custom:MIT/X')
depends=(libxrandr)
optdepends=()
makedepends=(git)
checkdepends=()
provides=(slock)
conflicts=(slock)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd slock-ashin
  printf "20170325.35633d4.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd slock-ashin
  make PREFIX=/usr 
}

package() {
  cd slock-ashin  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}

