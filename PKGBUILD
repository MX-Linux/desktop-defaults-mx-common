# Maintainer: dolphinoracle <dolphinoracle@gmail.com>
pkgname=desktop-defaults-mx-common
pkgver=25.10.01mx25
pkgrel=1
pkgdesc="Common desktop defaults for MX Linux"
arch=('any')
url="http://antix.mepis.org"
license=('GPL2')
depends=()
source=()
md5sums=()
PKGEXT='.pkg.tar.zst'

package() {
    cd "$srcdir/.."

    # Install icons
    install -dm755 "$pkgdir/usr/share/icons"
    cp -r icons/* "$pkgdir/usr/share/icons/"

    # Install X11 configuration
    install -dm755 "$pkgdir/etc/X11"
    cp -r X11/* "$pkgdir/etc/X11/"

    # Install udev rules
    install -dm755 "$pkgdir/etc/udev/rules.d"
    cp rules.d/* "$pkgdir/etc/udev/rules.d/"

    # Install modprobe configuration
    install -dm755 "$pkgdir/etc/modprobe.d"
    install -m644 hang-on-shutdown.conf "$pkgdir/etc/modprobe.d/"
    install -m644 i915-power-saving.conf "$pkgdir/etc/modprobe.d/"
    install -m644 fbdev-blacklist-nvidia.conf "$pkgdir/etc/modprobe.d/"
    install -m644 kfd.conf "$pkgdir/etc/modprobe.d/"

    # Install Xorg configuration
    install -dm755 "$pkgdir/usr/share/X11/xorg.conf.d"
    install -m644 20-thinkpad.conf "$pkgdir/usr/share/X11/xorg.conf.d/"

    # Install init script
    install -dm755 "$pkgdir/etc/init.d"
    install -m755 umountnfs-alternative.sh "$pkgdir/etc/init.d/"

    # Install binaries
    install -dm755 "$pkgdir/usr/bin"
    install -m755 early-bg "$pkgdir/usr/bin/"
    install -m755 clock12or24 "$pkgdir/usr/bin/"

    # Install desktop directory
    install -dm755 "$pkgdir/usr/share/desktop-directories"
    install -m644 mx-tools.directory "$pkgdir/usr/share/desktop-directories/"

    # Install XDG menus
    install -dm755 "$pkgdir/etc/xdg"
    cp -r xdg/* "$pkgdir/etc/xdg/"

    # Install additional configuration files
    install -dm755 "$pkgdir/etc/modprobe.d"

    # Install PulseAudio client configuration
    install -dm755 "$pkgdir/etc/pulse/client.conf.d"
    install -m644 00-enable-autospawn.conf "$pkgdir/etc/pulse/client.conf.d/"
}
