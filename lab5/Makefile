obj-m+= driver.o
KDIR = /lib/modules/$(shell uname -r)/build
all:
	make -C $(KDIR) M=$(shell pwd) modules

start:
	sudo insmod driver.ko
	gcc -o progtester main.c
	sudo ./progtester
	
clean:
	sudo rnmod driver.ko
	make -C $(KDIR) M=$(shell pwd) clean