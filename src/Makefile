KERNEL ?= /lib/modules/$(shell uname -r)/build
obj-m += xpad.o
all:
	make -C $(KERNEL) M=$(PWD) modules
install:
	make -C $(KERNEL) M=$(PWD) modules
	rm -rf xpad.ko.xz
	xz xpad.ko
	sudo cp -rf "xpad.ko.xz" "/lib/modules/$(uname -r)/kernel/drivers/input/joystick/xpad.ko.xz"
	sudo rmmod xpad
	sudo insmod "/lib/modules/$(uname -r)/kernel/drivers/input/joystick/xpad.ko.xz"
clean:
	make -C $(KERNEL) M=$(PWD) clean
