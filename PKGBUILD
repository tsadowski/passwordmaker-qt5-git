# Maintainer: Torsten Sadowski <tsadowski at gmx dot net>

pkgname=passwordmaker-qt5-git
pkgver=0.5.r6.aaeef9d
pkgrel=1
epoch=0
pkgdesc='PasswordMaker Desktop'
arch=('x86_64')
url='https://passwordmaker.org/'
license=('GPL')
depends=('qt5-svg' 'qt5-base')
makedepends=('git' 'qt5-tools')
provides=('passwordmaker-qt5')
conflicts=('passwordmaker-qt5')
source=("${pkgname}::git+https://github.com/tsadowski/passwordmaker-qt5.git")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  printf "0.5.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
    cd "${srcdir}"
    mkdir -p build
    cd build
    qmake PREFIX="${pkgdir}/usr" "../${pkgname}"
    make
}

package() {
    cd "${srcdir}/build"

    make install
}
