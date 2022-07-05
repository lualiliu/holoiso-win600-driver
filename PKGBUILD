pkgname=holoiso-win600-driver
pkgver="snapshot$(date +%Y%m%d.%H%M)"
pkgdesc="HoloISO Win600 Driver"
pkgrel="1"
depends=('gcc')
arch=("x86_64")

package() {
    sudo rm -rf "/lib/modules/$(uname -r)/kernel/drivers/input/joystick/xpad.ko.xz"
	make -f "${srcdir}/Makefile" install
	sudo cp -rf "${srcdir}/xpad.ko.xz" "/lib/modules/$(uname -r)/kernel/drivers/input/joystick/xpad.ko.xz"
    sudo insmod "/lib/modules/$(uname -r)/kernel/drivers/input/joystick/xpad.ko.xz"
}

