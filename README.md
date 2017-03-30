#  gererate | run | configure vm image (qemu+kvm) for miZy system building and other tests

## GENERATE

    mkdir /tmp/zero_builder
    cd /tmp/zero_builder
    ./miZy_builder_vm_generate yes

## RUN
    
    cd /tmp/zero_builder
    ./miZy_builder_vm start

## GET 

same possible to download already generated image from net

    cd /tmp/zero_builder
    ./miZy_builder_vm_image get
    ./miZy_builder_vm start

## miZy 
 
miZy - open source minimalistic tiny fast embedded Linux system, (for sunxi Orange Pi Zero, another sunxi boards maybe work too )

## LINKS

- [https://github.com/hyphop/miZy-builder](https://github.com/hyphop/miZy-builder)
- [https://github.com/hyphop/miZy-linux-kernel](https://github.com/hyphop/miZy-linux-kernel)
- [https://github.com/hyphop/miZy-uboot](https://github.com/hyphop/miZy-uboot)
- [https://hyphop.github.io/mizy/](https://hyphop.github.io/mizy/)

## ;)

![miZy](pics/miZy.logo.bw128x64x2.png)
