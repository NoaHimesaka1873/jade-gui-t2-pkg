# Maintainer: Rudra Saraswat <rs2009@ubuntu.com>
# Original maintainer: Crystal Linux Distribution Team <distribution@lists.getcryst.al>

pkgname=jade-gui-t2
pkgver=1.9.3
pkgrel=1
pkgdesc='Libadwaita based GUI front-end for blend-inst for Macs with T2 chip'
license=('GPL3')
arch=('x86_64' 'aarch64')
url="https://github.com/NoaHimesaka1873/jade-gui-t2"
depends=('blend-inst' 'openssl' 'libadwaita' 'python-pytz' 'gparted' 'vte4' 'gtksourceview5' 'python-tzlocal' 'python-requests' 'reflector')
makedepends=('meson' 'ninja' 'desktop-file-utils' 'appstream-glib' 'gtk4')
source=("git+${url}.git"
        "installer-autostart.desktop")
sha256sums=('SKIP'
            'SKIP')

build() {
    cd "jade-gui"
    meson setup --prefix="/usr" _build
    ninja -C _build
}

package() {
    cd "jade-gui/_build"
    DESTDIR="${pkgdir}" ninja install
    install -Dm755 ../../installer-autostart.desktop -t "${pkgdir}"/etc/xdg/autostart/
}
