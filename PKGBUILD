# Maintainer: Darkfish Tech <arch at darkfish dot com dot au>

pkgname=globalprotect-bin
pkgver=6.1.1.0
pkgrel=49
pkgdesc="GlobalProtect VPN Client Agent for University of Melbourne"
arch=('x86_64')
url="https://vpn.unimelb.edu.au"
license=('custom')
groups=()
depends=('qt5-webkit' 'wmctrl')
options=()
install=globalprotect.install
source=(
    "GlobalProtect_UI_focal_deb-$pkgver-$pkgrel.deb"
    "uom-pangps.xml"
    )
sha256sums=(
    'd128069b1cc9715d6cb18c239a6ca5a0f135d23df8c93a2de7ba0e40e92d80f7'
    '560221b4cdd8d4aae74a76a1a2c2ca0dd48edb9fd37ae83000aca8d87d4d625d'
    )
package() {
    tar -xf data.tar.xz -C "$pkgdir/"

    # Adapted for Arch Linux from debian package postinst
    GPDIR="$pkgdir/opt/paloaltonetworks/globalprotect"
    
    # Install system and user services
    install -Dm644 $GPDIR/gpd.service "$pkgdir/usr/lib/systemd/system/gpd.service"
    install -Dm644 $GPDIR/gpa.service "$pkgdir/usr/lib/systemd/user/gpa.service"

    # Install desktop and autostart files
    install -Dm644 $GPDIR/gp.desktop "$pkgdir/usr/share/applications/gp.desktop"
    install -Dm644 $GPDIR/PanGPUI.desktop "$pkgdir/etc/xdg/autostart/PanGPUI.desktop"

    # Install executables
    install -Dm755 $GPDIR/globalprotect "$pkgdir/usr/bin/globalprotect"
    install -Dm755 $GPDIR/PanGPUI "$pkgdir/usr/bin/PanGPUI"

    # Install custom configuration for UoM
    install -Dm644 "$srcdir"/uom-pangps.xml $GPDIR/pangps.xml

}
