 #Layers basic Commands
  
 #Show Layers - bblayers.conf
 bitbake-layers show-layers
  
#Create Layer
bitbake-layers create-layer <path/to/layer>
  
#Add Layer
bitbake-layers add-layer <path/to/layer>
  
  
 #Example create &  Add layer
 bitbake-layers create-layer /YoctoStudent/meta-student
 bitbake-layers add-layer  /YoctoStudent/meta-student/
  
bitbake-layers show-layers

#After create and add :
tree /YoctoStudent/meta-student/
/YoctoStudent/meta-student/
|-- COPYING.MIT
|-- README
|-- conf
|   `-- layer.conf
`-- recipes-example
    `-- example
        `-- example_0.1.bb
  
 

Poky Link Referance:
https://github.com/CESARBR/poky

