# Maintainer: Noa Himesaka <himesaka@noa.codes>
# Original Maintainer: Rudra Saraswat <rs2009@ubuntu.com>
# Original Original maintainer: Crystal Linux Distribution Team <distribution@lists.getcryst.al>

pkgname=jade-gui-t2
pkgver=1.9.4
pkgrel=1
pkgdesc='Libadwaita based GUI front-end for blend-inst for Macs with T2 chip'
license=('GPL3')
arch=('x86_64' 'aarch64')
url="https://github.com/NoaHimesaka1873/jade-gui-t2"
depends=('blend-inst-t2' 'openssl' 'libadwaita' 'python-pytz' 'gparted' 'vte4' 'gtksourceview5' 'python-tzlocal' 'python-requests' 'reflector')
makedepends=('meson' 'ninja' 'desktop-file-utils' 'appstream-glib' 'gtk4')
source=("git+file://[BASE_ASSEMBLE_PATH]/projects/jade-gui"
        "installer-autostart.desktop")
sha256sums=('SKIP'
            'SKIP')

build() {
    cd "jade-gui-t2"
    meson setup --prefix="/usr" _build
    ninja -C _build
}

package() {
    cd "jade-gui-t2/_build"
    DESTDIR="${pkgdir}" ninja install
    install -Dm755 ../../installer-autostart.desktop -t "${pkgdir}"/etc/xdg/autostart/
}
