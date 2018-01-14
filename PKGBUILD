# Maintainer: hensur <me@hensur.de>

pkgname='yoga370d-git'
_pkgname='yoga370d'
pkgver=r18.37e99a7
pkgrel=1
pkgdesc='A python daemon which automatically enables tablet mode on the Thinkpad Yoga 370'
url="https://github.com/hensur/yoga370d"
source=('yoga370d::git+https://github.com/hensur/yoga370d')
license=('GPL3')
arch=('any')
depends=('xorg-xrandr' 'acpid' 'python-dbus' 'iio-sensor-proxy' 'python-docopt' 'xorg-xinput' 'xf86-input-wacom' 'python')
md5sums=('SKIP')
makedepends=('git')

pkgver() {
    cd "$_pkgname"
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
    cd $srcdir/$_pkgname
    # yoga370d binary
    install -Dm755 "yoga370d" "${pkgdir}/usr/local/bin/yoga370d"

    # ThinkPad Yoga Desktop File
    install -Dm644 "${_pkgname}.desktop" "${pkgdir}/usr/share/applications/${_pkgname}.desktop"
}
