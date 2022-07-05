KERNEL ?= /lib/modules/$(shell uname -r)/build
obj-m += xpad.o
all:
	make -C $(KERNEL) M=$(PWD) modules
install:
	make -C $(KERNEL) M=$(PWD) modules
	rm -rf xpad.ko.xz
	xz xpad.ko
clean:
	make -C $(KERNEL) M=$(PWD) clean
