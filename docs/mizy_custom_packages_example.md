## mizy_custom_packages_example

```
mizy@mizy-desktop:/home/zero_builder$ ls -l1
total 638744
-rw-r--r-- 1 mizy mizy 156577792 дек 17 19:57 miZyBldr.squashfs
-rw-r--r-- 1 mizy mizy 497549312 дек 18 06:28 mizy.img

mizy@mizy-desktop:/home/zero_builder$ git clone https://github.com/hyphop/miZy-builder
Cloning into 'miZy-builder'...
remote: Counting objects: 284, done.
remote: Compressing objects: 100% (20/20), done.
remote: Total 284 (delta 4), reused 17 (delta 2), pack-reused 261
Receiving objects: 100% (284/284), 47.27 KiB | 0 bytes/s, done.
Resolving deltas: 100% (150/150), done.
Checking connectivity... done.

mizy@mizy-desktop:/home/zero_builder$ cd miZy-builder/
mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ls -l1
total 112
lrwxrwxrwx 1 mizy mizy     7 дек 18 10:04 ## hyphop ## -> LICENSE
-rw-rw-r-- 1 mizy mizy  1337 дек 18 10:04 LICENSE
-rw-rw-r-- 1 mizy mizy   383 дек 18 10:04 make_it_easy
-rwxrwxr-x 1 mizy mizy   124 дек 18 10:04 miZy_builder_clean
-rwxrwxr-x 1 mizy mizy  8424 дек 18 10:04 miZy_builder_vm
-rw-rw-r-- 1 mizy mizy    92 дек 18 10:04 miZy_builder_vm.conf
-rwxrwxr-x 1 mizy mizy    63 дек 18 10:04 miZy_builder_vm_disk_make
-rwxrwxr-x 1 mizy mizy    59 дек 18 10:04 miZy_builder_vm_disk_make_backing
-rwxrwxr-x 1 mizy mizy   300 дек 18 10:04 miZy_builder_vm.example
-rwxrwxr-x 1 mizy mizy   259 дек 18 10:04 miZy_builder_vm.example2
-rwxrwxr-x 1 mizy mizy 11505 дек 18 10:04 miZy_builder_vm_generate
-rw-rw-r-- 1 mizy mizy    99 дек 18 10:04 miZy_builder_vm_generate.conf
-rw-rw-r-- 1 mizy mizy   149 дек 18 10:04 miZy_builder_vm_generate.nomod
-rw-rw-r-- 1 mizy mizy    56 дек 18 10:04 miZy_builder_vm_generate.pub
-rwxrwxr-x 1 mizy mizy   248 дек 18 10:04 miZy_builder_vm.get
-rwxrwxr-x 1 mizy mizy  1166 дек 18 10:04 miZy_builder_vm_image
-rw-rw-r-- 1 mizy mizy   302 дек 18 10:04 miZy_builder_vm.net.conf
lrwxrwxrwx 1 mizy mizy    30 дек 18 10:04 miZy_builder_vm.nomod.no -> miZy_builder_vm_generate.nomod
-rwxrwxr-x 1 mizy mizy    99 дек 18 10:04 miZy_builder_vm.run
-rwxrwxr-x 1 mizy mizy   130 дек 18 10:04 miZy_builder_vm.run2
-rwxrwxr-x 1 mizy mizy  1173 дек 18 10:04 miZy_builder_vm_squash
-rwxrwxr-x 1 mizy mizy   347 дек 18 10:04 miZy_builder_vm_test
drwxrwxr-x 2 mizy mizy  4096 дек 18 10:04 pics
-rw-rw-r-- 1 mizy mizy  3349 дек 18 10:04 README.md
drwxrwxr-x 2 mizy mizy  4096 дек 18 10:04 scripts
drwxrwxr-x 2 mizy mizy  4096 дек 18 10:04 tools

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ./miZy_builder_vm_disk_make_backing ../mizy.img mizy.img
Formatting 'mizy.img', fmt=qcow2 size=8589934592 backing_file=../mizy.img encryption=off cluster_size=65536 lazy_refcounts=off refcount_bits=16

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ln -s ../miZyBldr.squashfs miZyBldr.squashfs

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ sudo ./miZy_builder_vm.example

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ps -AF|grep qemu
8631  8630 31 760970 198184 0 10:21 pts/9    00:00:07 qemu-system-x86_64

### ok 

### may be need if u dont have 
### ssh-keygen

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ./miZy_builder_vm.example2 
[i] add pub key /home/mizy/.ssh/id_rsa.pub
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/mizy/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
root@vvv's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'root@vvv'"
and check to make sure that only the key(s) you wanted were added.

### ok we can login via pub key

mizy@mizy-desktop:/home/zero_builder/miZy-builder$ ssh root@vvv

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Mon Dec 18 05:24:44 2017 from hst
root@miZyBldr:~# 

## may be change default password
## root@miZyBldr:~# passwd 

root@miZyBldr:~# cd /tmp/zero_builder/
root@miZyBldr:/tmp/zero_builder# ls -l1
total 63856
-rw-r--r--  1 root root 32911360 May 26  2017 OpenWrt-SDK-sunxi_gcc-5.3.0_musl-1.1.16_eabi.Linux-x86_64.squashfs
drwx------  2 root root    16384 Dec 17 15:38 lost+found
drwxr-xr-x 12 root root     4096 Dec 17 15:55 miZy-openwrt-sdk
drwxr-xr-x  2 root root     4096 Dec 17 15:55 toolchain-arm_cortex-a8.vfpv3_gcc-5.3.0_musl-1.1.16_eabi
-rw-r--r--  1 root root 32452608 May 26  2017 toolchain-arm_cortex-a8.vfpv3_gcc-5.3.0_musl-1.1.16_eabi.squashfs

root@miZyBldr:/tmp/zero_builder# cd miZy-openwrt-sdk/

# may be pull changes from git
# root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# git pull

# make second prepare 
root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# ./openwrt.sdk.prepare2
[i] working dir ./openwrt mounted as overlay  RO: ./openwrt.ro RW: ./openwrt.rw
[i] mount -o ro ../toolchain-arm_cortex-a8.vfpv3_gcc-5.3.0_musl-1.1.16_eabi.squashfs ../toolchain-arm_cortex-a8.vfpv3_gcc-5.3.0_musl-1.1.16_eabi

## ok !!! now we are ready for packages building

```
### folders

`bin` - packages tree

```    
root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# find bin
bin
bin/sunxi
bin/sunxi/packages
bin/sunxi/packages/mizy
bin/sunxi/packages/mizy/Packages.gz
bin/sunxi/packages/mizy/Packages
bin/sunxi/packages/mizy/sunxi-tools_1.4.0-1_sunxi.ipk
bin/sunxi/packages/packages
bin/sunxi/packages/packages/Packages.gz
bin/sunxi/packages/packages/Packages
bin/sunxi/packages/base
bin/sunxi/packages/base/librt_1.1.16-1_sunxi.ipk
bin/sunxi/packages/base/Packages.gz
bin/sunxi/packages/base/libpthread_1.1.16-1_sunxi.ipk
bin/sunxi/packages/base/Packages
bin/sunxi/packages/base/libc_1.1.16-1_sunxi.ipk
bin/sunxi/packages/base/libatomic_5.3.0-1_sunxi.ipk
bin/sunxi/packages/base/libstdcpp_5.3.0-1_sunxi.ipk
bin/sunxi/packages/base/libusb-1.0_1.0.20-1_sunxi.ipk
bin/sunxi/packages/base/libgcc_5.3.0-1_sunxi.ipk
bin/sunxi/packages/kernel
bin/sunxi/packages/kernel/Packages.gz
bin/sunxi/packages/kernel/Packages

```

`dl` - downloaded sources

```
root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# find dl
dl
dl/sunxi-tools-1.4.0-7128c73abf88eef9332ce7a9cb11704f35ad516c.tar.gz
dl/libusb-1.0.20.tar.bz2
```

`mizy-feeds` - custom feeds

```
root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# find mizy-feeds/markdown/
mizy-feeds/markdown/
mizy-feeds/markdown/Makefile
```

## build custom package example 

```
root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# ./openwrt.sdk.feed update -i       
Create index file './feeds/base.index' 
Create index file './feeds/packages.index' 
Create index file './feeds/mizy.index' 

root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# ./openwrt.sdk.feed install markdown
Installing package 'markdown' from mizy

root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# ./openwrt.sdk.make
...
 make[1] world
 make[2] package/compile
...
 make[3] -C /tmp/zero_builder/miZy-openwrt-sdk/mizy-feeds/markdown compile
...
 make[2] package/index

## ok u can get it from there

root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# find bin/sunxi/packages/mizy
bin/sunxi/packages/mizy
bin/sunxi/packages/mizy/Packages.gz
bin/sunxi/packages/mizy/Packages
bin/sunxi/packages/mizy/markdown_0.1-1_sunxi.ipk
bin/sunxi/packages/mizy/sunxi-tools_1.4.0-1_sunxi.ipk

## mizy fix openwrt deps 

root@miZyBldr:/tmp/zero_builder/miZy-openwrt-sdk# ./openwrt.pkg.fix

## now u can open/use  mizy repo

mizy@mizy-desktop:~$ wget -q -O- http://vvv/sunxi/packages/mizy
<pre><a href='Packages'>Packages</a>
<a href='Packages.gz'>Packages.gz</a>
<a href='markdown_0.1-1_sunxi.ipk'>markdown_0.1-1_sunxi.ipk</a>
<a href='sunxi-tools_1.4.0-1_sunxi.ipk'>sunxi-tools_1.4.0-1_sunxi.ipk</a>


## ok check in mizy

#add miZyBldr host as vvv
echo 10.168.1.1 vvv >> /etc/hosts

# setup repo
echo "src local_mizy http://vvv/sunxi/packages/mizy" > /etc/opkg/local.conf

# check it now

root@miZy:/etc/opkg# opkg update
Downloading http://downloads.openwrt.org/snapshots/trunk/sunxi/generic/packages/base/Packages.gz.
Updated list of available packages in /var/opkg-lists/designated_driver_base.
Downloading http://downloads.openwrt.org/snapshots/trunk/sunxi/generic/packages/packages/Packages.gz.
Updated list of available packages in /var/opkg-lists/designated_driver_packages.
Downloading http://vvv/sunxi/packages/mizy/Packages.
Updated list of available packages in /var/opkg-lists/local_mizy.

root@miZy:/etc/opkg# opkg list | grep markdown
markdown - 0.1-1 - markdown c parser convert to html

root@miZy:/etc/opkg# opkg install markdown
Installing markdown (0.1-1) to root...
Downloading http://vvv/sunxi/packages/mizy/markdown_0.1-1_sunxi.ipk.
Configuring markdown.

root@miZy:/etc/opkg# markdown --version
Built with Hoedown 3.0.7.

## ok done

```
