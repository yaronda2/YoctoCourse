##############################################################################
#                             Yocto Course beginner
#
# Step by step to Download and install Yocto basic layers of kirstone version
#
# Require Ubuntu 20.04 / Ubuntu 22.04
#
#
################################################################################


#create Folder
sudo mkdir /YoctoStudent

#Give permission
sudo chown -R <user_name> /YoctoStudent
cd /YoctoStudent

#Install require packages

sudo apt install gawk wget git diffstat unzip texinfo gcc build-essential chrpath socat cpio python3 python3-pip python3-pexpect xz-utils debianutils iputils-ping python3-git python3-jinja2 python3-subunit zstd liblz4-tool file locales libacl1


sudo locale-gen en_US.UTF-8

#Clone poky
git clone git://git.yoctoproject.org/poky

#Checkout to branch kirkstone
cd poky
git checkout -t origin/kirkstone -b my-kirkstone

#Source Enviorment yocto
. oe-init-build-env

export LC_ALL=C

#Build - warning this command can take a few hours
bitbake core-image-minimal

#After Succes image build run the emulator
runqemu

