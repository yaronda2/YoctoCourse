### Xilinx BSP 

#Download Xilinx layers 

mkdir ~/xilinx
cd ~/xilinx
git clone https://github.com/Xilinx/meta-xilinx.git -b kirkstone-next
git clone https://github.com/Xilinx/meta-xilinx-tools.git -b kirkstone-next

bitbake-layers add-layer ~/xilinx/meta-xilinx/meta-xilinx-core/
bitbake-layers add-layer ~/xilinx/meta-xilinx/meta-xilinx-bsp/
bitbake-layers add-layer ~/xilinx/meta-xilinx-tools/

git clone -b kirkstone https://git.openembedded.org/meta-openembedded.git
bitbake-layers add-layer ~/meta-openembedded/meta-oe/

Machine example location:
https://github.com/Xilinx/meta-xilinx/blob/master/meta-xilinx-bsp/conf/machine/zcu102-zynqmp.conf
