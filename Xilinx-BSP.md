### Xilinx BSP 

#Download Xilinx layers 

mkdir ~/xilinx
cd ~/xilinx
git clone https://github.com/Xilinx/meta-xilinx.git -b kirkstone-next
git clone https://github.com/Xilinx/meta-xilinx-tools.git -b kirkstone-next

bitbake-layers add-layer ~/xilinx/meta-xilinx/meta-xilinx-core/
bitbake-layers add-layer ~/xilinx/meta-xilinx/meta-xilinx-bsp/
