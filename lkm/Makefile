obj-m += sasuke.o
sasuke-y := check_netfilter_hooks.o check_processes.o check_syscalls.o count_modules.o include.o main.o
#ccflags-y = -std=gnu99 -Wno-declaration-after-statement
#ccflags-y = -DDEBUG -std=gnu99 -Wno-declaration-after-statement
ccflags-y = -DDEBUG

all:	sysmap
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

sysmap:
	./gensysmap.sh
	@echo "Generated sysmap.h"

clean:
	@rm -f sysmap.h
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean

