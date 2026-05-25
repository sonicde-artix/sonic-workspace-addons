# Maintainer: callmetango
# Contributor: artist <artist@artixlinux.org>

pkgname=sonic-workspace-addons
pkgver=6.6.5
pkgrel=2
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
sha256sums=('7bf8026d691f706954db7bc3ca2265972d048ea5eb2cae03e49f6e7b5beee9cf')

build() {
  cmake -B build  -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
