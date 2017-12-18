## mizy image

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

```
