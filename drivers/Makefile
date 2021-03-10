KDIR ?= /lib/modules/`uname -r`/build

default:
	$(MAKE) -C $(KDIR) M=$(PWD)

load_rdma:
	sudo insmod fastswap_rdma.ko sport=50000 sip="10.0.0.18" cip="10.0.0.17" nq=8
	sudo insmod fastswap.ko

unload_rdma:
	sudo rmmod fastswap.ko
	sudo rmmod fastswap_rdma.ko

load_dram:
	sudo insmod fastswap_dram.ko
	sudo insmod fastswap.ko

unload_dram:
	sudo rmmod fastswap.ko
	sudo rmmod fastswap_dram.ko

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean

help:
	$(MAKE) -C $(KDIR) M=$(PWD) help
