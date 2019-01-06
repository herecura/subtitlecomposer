# Contributor: Mladen Milinkovic <maxrd2@smoothware.net>
# Maintainer: Mladen Milinkovic <maxrd2@smoothware.net>

pkgname=subtitlecomposer
pkgver=0.6.6
pkgrel=2
pkgdesc="A KDE subtitle editor"
arch=('x86_64')
url="https://github.com/maxrd2/subtitlecomposer"
license=('GPL')
depends=('kcoreaddons' 'sonnet' 'kcodecs' 'kross' 'kxmlgui' 'ki18n' 'gstreamer')
makedepends=('extra-cmake-modules')
# Comment/uncomment the following dependencies to disable/enable
# building of plugins for MPV and Xine player backends.
makedepends+=('xine-lib')
makedepends+=('mpv')
optdepends=('mpv: for MPV backend'
    'mplayer: for MPlayer backend'
    'xine-lib: for Xine backend'
    'ruby: for scripting'
    'python: for scripting'
)
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/maxrd2/${pkgname}/archive/v${pkgver}.tar.gz")
sha256sums=('6cd1d74f7934cdaa5d492f47da4143bd096a6196f2afcb2827cada9a3cdb2ea4')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  cmake \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
    -DBUILD_TESTING=OFF
    make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
    make DESTDIR=${pkgdir} install
}
