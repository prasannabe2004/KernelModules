ifeq ($(KERNELRELEASE),)

KERNELDIR ?= /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)
.PHONY: build clean

build:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules
	gcc -o mmap mmapUser.c

clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod.c modules.order Module.symvers .tmp_versions mmap
else
$(info Building with KERNELRELEASE = ${KERNELRELEASE})
obj-m := mmapModule.o

endif



