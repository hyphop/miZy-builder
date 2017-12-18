#  gererate | run | configure vm image (qemu+kvm) for miZy building system and other tests

## GET SCRIPTS
    
    mkdir /tmp/zero_builder
    cd /tmp/zero_builder
    git clone https://github.com/hyphop/miZy-builder

## GENERATE vm Images

    cd /tmp/zero_builder/miZy-builder
    ./miZy_builder_vm_generate yes			  # debian stable (stretch) # not tested
    # or run  via sudo, becouse DEBOOTSTRAP need root
    sudo ./miZy_builder_vm_generate yes 
    #
    ver=xenial ./miZy_builder_vm_generate  yes  # ubuntu xenial # miZy-openwrt-sdk ok
    ver=jessie ./miZy_builder_vm_generate  yes  # debian jessie # miZy-openwrt-sdk ok
    ver=wheezy ./miZy_builder_vm_generate  yes  # debian wheezy # 

## RUN EXAMPLES
    
    cd /tmp/zero_builder/miZy-builder
    ./miZy_builder_vm start
    ./miZy_builder_vm start run=tar=scripts
    ./miZy_builder_vm start run=http://...

## DEBOOTSTRAP FIX

	cd /usr/share/debootstrap/scripts
	ln -s gutsy xenial
	ln -s sid jessie

setup total ram size

    mem=4G ./miZy_builder_vm start

setup root password 

    password=1234 ./miZy_builder_vm start

daemon mode 

    console=no password=1234 ./miZy_builder_vm start

## Easy make - by one-line command

    wget http://raw.githubusercontent.com/hyphop/miZy-builder/master/make_it_easy -O- | sh -

## files & configs

* miZy_builder_vm.net.conf	- vm net config
* miZy_builder_vm.conf		- vm config
* miZy_builder_vm.get		- download last miZyBldr.squashfs from 
    https://github.com/hyphop/pkg/releases/download/mirror/miZyBldr.squashfs

## OVERLAY

create overlay

    qemu-img create -f qcow2 miZyBldr.ovl 1G

run with 

    ./miZy_builder_vm start ovl=

## PERSISTENT STORAGE

create qemu image

    qemu-img create -f qcow2 mizy.img 8G

run vm with image

    ./miZy_builder_vm start disk=mizy.img

prepare & use image inside vm

    mkfs.ext4 /dev/vdb
    e2label /dev/vdb mizy_build
    blkid 
	/dev/vda: TYPE="squashfs"
	/dev/vdb: LABEL="mizy_build" UUID="..." TYPE="ext4"
    mkdir /tmp/zero_builder
    mount /dev/vdb /tmp/zero_builder
    df | grep zero
	/dev/vdb         8125880  18420   7671648   1% /tmp/zero_builder
    cd /tmp/zero_builder
    ...

## run script

	ssh root@vvv sh < ./scripts/miZy.build.script

## DOWNLOAD IMAGE

yes u can download and use already generated image withot any preparation )
sure! you must trust for this image or generate image by himself!

    cd /tmp/zero_builder/miZy-builder
    ./miZy_builder_vm_image get
    ./miZy_builder_vm start

### DEFAULT NET IMAGE NOT HAVE ANY authorized_keys

    root@miZyBldr:~# cat ~/.ssh/authorized_keys 
    ## put fixed authorized_keys there
    ## yes is empty there
    ## get from ./miZy_builder_vm_generate.pub
    ## miZy_builder_vm_generate.pub
    ## yes is empty there

### ADD ssh authorized_keys

	ssh-copy-id -i ~/.ssh/id_rsa.pub root@vvv

## miZy 
 
miZy - open source minimalistic tiny fast embedded Linux system, (for sunxi Orange Pi Zero, another sunxi boards maybe work too )

## LINKS

- [https://github.com/hyphop/miZy-builder](https://github.com/hyphop/miZy-builder)
- [https://github.com/hyphop/miZy-linux-kernel](https://github.com/hyphop/miZy-linux-kernel)
- [https://github.com/hyphop/miZy-uboot](https://github.com/hyphop/miZy-uboot)
- [https://hyphop.github.io/mizy/](https://hyphop.github.io/mizy/)

## ;)

![miZy](pics/miZy.logo.bw128x64x2.png)
