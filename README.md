#  gererate | run | configure vm image (qemu+kvm) for miZy building system and other tests

## GET SCRIPTS
    
    mkdir /tmp/zero_builder
    cd /tmp/zero_builder
    git clone https://github.com/hyphop/miZy-builder

## GENERATE

    cd /tmp/zero_builder/miZy-builder
    ./miZy_builder_vm_generate yes

## RUN
    
    cd /tmp/zero_builder/miZy-builder
    ./miZy_builder_vm start
    ./miZy_builder_vm start run=tar=scripts
    ./miZy_builder_vm start run=http://...

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

## miZy 
 
miZy - open source minimalistic tiny fast embedded Linux system, (for sunxi Orange Pi Zero, another sunxi boards maybe work too )

## LINKS

- [https://github.com/hyphop/miZy-builder](https://github.com/hyphop/miZy-builder)
- [https://github.com/hyphop/miZy-linux-kernel](https://github.com/hyphop/miZy-linux-kernel)
- [https://github.com/hyphop/miZy-uboot](https://github.com/hyphop/miZy-uboot)
- [https://hyphop.github.io/mizy/](https://hyphop.github.io/mizy/)

## ;)

![miZy](pics/miZy.logo.bw128x64x2.png)
