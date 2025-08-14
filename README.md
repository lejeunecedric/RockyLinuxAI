This is my journey through the setup of an AI PC under Rocky Linux. 
I picked my DELL Precision 7520 that has a Quadro M220 GPU and 16 GB of RAM, not the most impressive machine but a good starting point to try things with no counter on.

#August 14
Downloading and installing Rocky Linux 9.6 with KDE

##Installing NVidia drivers. 
That's a bit of an adventure, as it's always been ! 
It's still possible to end up with a black screen, as in the old days. 

###Rocky documentations
https://docs.rockylinux.org/desktop/display/installing_nvidia_gpu_drivers/
Didn't work
###Rocky forums 
https://forums.rockylinux.org/t/nvidia-drivers-on-rocky-linux/12366
Didn't work
###Linux Capable
https://linuxcapable.com/how-to-install-nvidia-drivers-on-rocky-linux/

Removed all NVidia related stuff in the drivers with 
sudo dnf erase *nvidia* 
That's a bit of a brush but it seems to have left a clean place
found here : https://discussion.fedoraproject.org/t/quickest-most-efficient-method-to-uninstall-nvidia-drivers-including-cuda/76603/6

From what I understand, Linux NVidia drivers can be installed from different repos :
-Official RHEL, 
-
-RPMFulsion
-ELRepo

Finally the one that seems to have fixed it is 
sudo dnf install akmod-nvidia
found here : https://rpmfusion.org/Howto/NVIDIA#About_this_Howto

To explain the difference between a kmod and an akmod
https://linuxism.ustd.ip.or.kr/2015

Alo



#August 13
Trying different flavours of Linux, mostly Ubuntu based, and moving to Rocky Linux as it's the most common in the VFX/Animation world
You may wanna check https://vfxplatform.com/linux/
