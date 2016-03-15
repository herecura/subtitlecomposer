# Contributor: Mladen Milinkovic <maxrd2@smoothware.net>
# Maintainer: Mladen Milinkovic <maxrd2@smoothware.net>

pkgname=subtitlecomposer
pkgver=0.6.1
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
sha256sums=('a49c7b7e5d8f1137373a65c9110a0934da6d827a7362dd6e7face708582c1d51')

build() {
    cd ${srcdir}/subtitlecomposer-${pkgver}
    cmake -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd ${srcdir}/subtitlecomposer-${pkgver}
    make DESTDIR=${pkgdir} install
}
