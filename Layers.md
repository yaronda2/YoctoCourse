 #Layers basic Commands
 #Important note : to run these commands you must be located under 'build' directory.
 #Show Layers - bblayers.conf
 ```
 bitbake-layers show-layers
  ```
#Create Layer
```
bitbake-layers create-layer <path/to/layer>
```
  
#Add Layer
```
bitbake-layers add-layer <path/to/layer>
```  
  
 #Example create &  Add layer
 ```
 bitbake-layers create-layer ~/YoctoStudent/meta-student
 bitbake-layers add-layer  ~/YoctoStudent/meta-student/
 ```
bitbake-layers show-layers

```
layer                 path                                      priority
==========================================================================
meta                  /home/student/poky/meta                   5
meta-poky             /home/student/poky/meta-poky              5
meta-yocto-bsp        /home/student/poky/meta-yocto-bsp         5
meta-student          /home/student/YoctoStudent/meta-student   6
```

#After create and add :
```
tree ~/YoctoStudent/meta-student/
/YoctoStudent/meta-student/
|-- COPYING.MIT
|-- README
|-- conf
|   `-- layer.conf
`-- recipes-example
    `-- example
        `-- example_0.1.bb
  
 ```

Poky Link Referance:
https://github.com/CESARBR/poky

