***Practice :***
add .c program to image , to do it need to add the src .c file to recipe that will contain in a layer , to edit .bb recipe file according
and build it , finally need to add it to image.

***Steps:***
1)edit new recipe in studentlayer - you can use suitable simple .bb file from recipes.
2)add .c file to recipe folder (under <recipe_name>/files)
3)build the recipe - check it compiled
4)add it to image in local.conf

use example of simple recipe with .c file and modify the .c file to program of one of the https://www.programiz.com/c-programming/examples
#add source files 
#change summary and discription

#configure the recipe

#solution

***Tested***
```
cd ~/YoctoStudent/meta-student 
mkdir -p  recipes-apps/swap-numbers
cp recipes-example/example/example_0.1.bb recipes-apps/swap-numbers/swap-numbers_1.0.bb
mkdir recipes-apps/swap-numbers/files
cp recipes-apps/swap-numbers/swap.c  recipes-apps/swap-numbers/files
```

***edit file swap-numbers_1.0.bb***
```
SUMMARY = "swap-numbers app"
DESCRIPTION = "Swap numbers between 2 given numbers"
LICENSE = "MIT"

LIC_FILES_CHKSUM = "file://${COMMON_LICENSE_DIR}/MIT;md5=0835ade698e0bcf8506ecda2f7b4f302"

SRC_URI = "file://swap.c"

S = "${WORKDIR}"

do_compile() {
    ${CC} ${LDFLAGS} swap.c -o swap-numbers
}

do_install() {
    install -d ${D}${bindir}
    install -m 0755 swap-numbers ${D}${bindir}
}
```

***find the build in *** 
```
bitbake -e | grep ^WORKDIR
file  /var/yocto/tmp/work/core2-64-poky-linux/swap-numbers/
```

***to check recipes is layers installed***
```bitbake-layers show-recipes | grep swap```

***add package to os***
```
***add to local.conf***
IMAGE_INSTALL:append = " swap-numbers"
```
