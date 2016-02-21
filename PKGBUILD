# Contributor: Mladen Milinkovic <maxrd2@smoothware.net>
# Maintainer: Mladen Milinkovic <maxrd2@smoothware.net>

pkgname=subtitlecomposer
pkgver=0.5.9
pkgrel=1
pkgdesc="A KDE subtitle editor"
arch=('i686' 'x86_64')
url="https://github.com/maxrd2/subtitlecomposer"
license=('GPL')
depends=('kcoreaddons' 'sonnet' 'kcodecs' 'kio' 'kross' 'kxmlgui' 'ki18n' 'gstreamer')
#makedepends=('xine-lib' 'gstreamer' 'mpv' 'mplayer' 'extra-cmake-modules')
makedepends=('mplayer' 'extra-cmake-modules')
conflicts=('subtitlecomposer-git')
optdepends=(
    'mplayer: for MPlayer backend'
    #'mpv: for mpv backend'
    #'xine-lib: for Xine backend'
    'ruby: for scripting'
    'python: for scripting'
)
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/maxrd2/subtitlecomposer/archive/v${pkgver}.tar.gz")
sha256sums=('e3b23680dc2eacb5e5eaf8dbc3c9a61c092e0daab5110e86beb8e73099dd53c5')

build() {
    cd ${srcdir}/subtitlecomposer-${pkgver}
    cmake -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd ${srcdir}/subtitlecomposer-${pkgver}
    make DESTDIR=${pkgdir} install
}
