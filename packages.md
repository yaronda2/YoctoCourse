


##show all packages from layers
```
Bitbake-layers show-recipes 
```
##example of check packages
```
Bitbake-layers show-recipes python3
Bitbake-layers show-recipes git
```

##Add Packge 
```
***local.conf ***
IMAGE_INSTALL:append = " git"
```

