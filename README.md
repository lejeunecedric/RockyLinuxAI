This is my journey through the setup of an AI PC under Rocky Linux. 
I picked my DELL Precision 7520 that has a Quadro M220 GPU and 16 GB of RAM, not the most impressive machine but a good starting point to try things with no counter on.

#Day 3
Still struggling with the disable-cuda-malloc option that I can't get into ComfyUI to accommodate the missing feature in the 

##Environment management
Virtual environments are cool, because you can have specific libraries based on what you do, while leaving the system dealing with its own.
If you develop tools it's really necessary to have something you can easily package for the dependencies.
The problem is you have many options and it's easy to mix different ones, especially when looking for tricks on the interwebs.
The 
venv is part of th
I use conda because it comes with a full framework of tools Conda https://anaconda.com/app/

#Day 2
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
- Official RHEL, 
- RPEL
- RPMFulsion
- ELRepo
XXX

Finally the one that seems to have fixed it is 
sudo dnf install akmod-nvidia
found here : https://rpmfusion.org/Howto/NVIDIA#About_this_Howto

To explain the difference between a kmod and an akmod
https://linuxism.ustd.ip.or.kr/2015

#Installing ComfyUI
ComfyUI is a great tool to generate images, videos and more.
From my experience the basic install where you git clone the repo isn't great, but that maybe because of CUDA issues

Comfy CLI gives you a good way to control the whole thing
Also important to install Comfy Manager that is a great utility tool to manage a lot of things.

Still that annoying CUDA error on image generation 

##Installing LM Studio
LM Studio is a great little tool

##Installing VS Code
https://code.visualstudio.com/docs/setup/linux#_install-vs-code-on-linux

##Using Flatpak
Flatpak is a tool to install compiled apps. By default it doesn't have a repo linked, so you need to add Flathub
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

#Installing Podman
Podman is an open source replacement for Docker. It's installed by default but it doesn't ha

#Day 1
Trying different flavours of Linux, mostly Ubuntu based, and moving to Rocky Linux as it's the most common in the VFX/Animation world
You may wanna check https://vfxplatform.com/linux/
