# miningrig

to setup a new rig:

- update and dist-updgrade
- install libcurl3 and unzip
- mkdir claymoreV10.0
- untar claymore in claymoreV10.0 dir
- mv claymore\_config in claymore dir then unzip it and replace all files
- chmod u+x start.bash
- download amd drivers for ubuntu (17.40)
- untar amdgpu
- add user to video group
- ´./amdgpu-pro-install -y´
- add ´amdgpu.vm\_fragment\_size=9´ arg to **GRUB\_CMDLINE\_LINUX\_DEFAULT** in */etc/default/grub*
- reboot

´´´bash
sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get install libcurl3 unzip
mkdir claymoreV10.0
tar -xvf Claymore -C claymoreV10.0
mv claymore\_config\_nanopool.zip claymoreV10.0 && cd claymoreV10.0
unzip claymore\_config\_nanopool.zip
chmod u+x start.bash && cd ..
wget --referer=http://support.amd.com https://www2.ati.com/drivers/linux/ubuntu/amdgpu-pro-17.40-492261.tar.xz
tar -Jxvf amdgpu-pro
cd amdgpu-pro
sudo ./amdgpu-pro-install -y
sudo usermod -a -G video nature
sudo vim /etc/default/grub # And add module arg
sudo reboot
´´´
