# Contributor: Mladen Milinkovic <maxrd2@smoothware.net>
# Maintainer: Mladen Milinkovic <maxrd2@smoothware.net>

pkgname=subtitlecomposer
_pkgname=SubtitleComposer
pkgver=0.7.0
pkgrel=1
pkgdesc="A KDE subtitle editor"
arch=('x86_64')
url="https://github.com/maxrd2/subtitlecomposer"
license=('GPL')
depends=('kcoreaddons' 'sonnet' 'kcodecs' 'kross' 'kxmlgui' 'ki18n' 'ffmpeg')
makedepends=('extra-cmake-modules')

# Comment/uncomment the following dependencies to disable/enable
# building the plugins for MPV and Xine player backends
makedepends+=('xine-lib')
makedepends+=('mpv')

# For consistency, also enable/disable the corresponding optdepends
optdepends=('gstreamer: GStreamer videoplayer backend'
            'mpv: MPV videoplayer backend'
            'mplayer: MPlayer videoplayer backend'
            'phonon-qt5: Phonon videoplayer backend'
            'xine-lib: Xine videoplayer backend'
            'kross-interpreters: Ruby and Python scripting support'
            'ruby: scripting'
            'python: scripting')

source=("${pkgname}-${pkgver}.tar.gz::https://github.com/maxrd2/${pkgname}/archive/v${pkgver}.tar.gz")
sha256sums=('90dee806df0ee57f4098d417f62014b4533dbf5598d5535c9da1066536c1ed41')

build() {
    cd ${_pkgname}-${pkgver}
    cmake \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DLIB_INSTALL_DIR=lib \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DBUILD_TESTING=OFF \
        -DAPP_VERSION="${pkgver}"
    make
}

package() {
    cd ${_pkgname}-${pkgver}
    make DESTDIR=${pkgdir} install
}
