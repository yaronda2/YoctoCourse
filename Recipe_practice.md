#Create  recipe named my_first_recipe.bb
#add it to layer

use example of simple recipe with .c file and modify the .c file to program of one of the https://www.programiz.com/c-programming/examples
#add source files 
#change summary and discription

#configure the recipe

#solution
```
1)open URL https://www.programiz.com/c-programming/examples  - and choose one - for this example I used C `Program to Display Fibonacci Sequence` and copy code
2)go to meta-student/ layer directory
3)mkdir recipes-apps/<name_app>
4)create bb file and name it according to app name and add version -> for example if the app name is 'Fibonacci' 
5) located bb in : meta-student/recipes-apps/Fibonacci/Fibonacci_1.0.bb
5)open in edit mode the Fibonacci_1.0.bb file and add to the file the simple example - from recipes section
6)edit the SRC_URI variable and also made the change in do_install , summary , sections , do_compile.
7)mkdir files : meta-student/recipes-apps/Fibonacci/files
8)create the .c file according the name in .bb file and paste the source code from the URL and save.
9)run : bitbake Fibonacci
```

```
#Tested
~/YoctoStudent$ cd meta-student/
mkdir -p  recipes-apps/swap-numbers
cp recipes-example/example/example_0.1.bb recipes-apps/swap-numbers/swap-numbers_1.0.bb
mkdir recipes-apps/swap-numbers/files
cp recipes-apps/swap-numbers/swap.c  recipes-apps/swap-numbers/files

#edit file swap-numbers_1.0.bb

```
#find the build in  : 
bitbake -e | grep ^WORKDIR
file  /var/yocto/tmp/work/core2-64-poky-linux/swap-numbers/

#to check recipes in layers installed
bitbake-layers show-recipes | grep swap

#add package to os
add to lcoal.conf
IMAGE_INSTALL:append = " swap-numbers"

```
