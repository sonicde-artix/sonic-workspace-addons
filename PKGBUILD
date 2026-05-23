# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-workspace-addons
pkgver=6.6.5
pkgrel=1
pkgdesc='All kind of addons to improve your SonicDE experience'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-workspace-addons'
license=(LGPL-2.0-or-later)
depends=(glibc
         icu
         kcmutils
         kconfig
         kdbusaddons
         kdeclarative
         kholidays
         ki18n
         kiconthemes
         kitemmodels
         kjobwidgets
         knewstuff
         knotifications
         kpackage
         kservice
         ksvg
         kunitconversion
         kwidgetsaddons
         kxmlgui
         libgcc
         qt6-5compat
         qt6-base
         qt6-declarative
         qt6-quick3d
         sonic-frameworks-auth
         sonic-frameworks-core-addons
         sonic-frameworks-io
         sonic-frameworks-keybind
         sonic-frameworks-quick-ui
         sonic-frameworks-runner
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-win
         sonic-workspace
         sonnet)
makedepends=(extra-cmake-modules
             networkmanager-qt
             qt6-webengine)
optdepends=('networkmanager-qt: POTD wallpaper'
            'qt6-webengine: dictionary and webbrowser applets'
            'quota-tools: disk quota applet')
groups=(sonicde)
conflicts=(kdeplasma-addons)
replaces=(kdeplasma-addons)
provides=(kdeplasma-addons)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('2d568f4a1523e914d10c433837c888f8c34e11954d10467cf9b09ee752298a4d')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
