- Install WSL -
wsl --install
______________
This command will enable the required optional components, 
download the latest Linux kernel, set WSL 2 as your default, 
and install a Linux distribution for you (Ubuntu by default)

- Configure WSL-
sudo apt update && sudo apt upgrade
______________
This checks the version (Run this in Powershell)
wsl -l -v

- Ubuntu GUI-
sudo apt install -y xrdp
sudo apt install -y xfce4
sudo apt install -y xfce4-goodies
______________

sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
echo xfce4-session > ~/.xsession

sudo nano /etc/xrdp/startwm.sh
-comment these lines below-
#test -x /etc/X11/Xsession && exec /etc/X11/Xsession
#exec /bin/sh /etc/X11/Xsession

- add these lines-
# xfce
startxfce4
______________
- Start RDP Service-
sudo /etc/init.d/xrdp start
______________

Refrences:
https://github.com/davidbombal/wsl2/blob/main/ubuntu_gui_youtube
https://docs.microsoft.com/en-us/windows/wsl/install
- Intall Windows Terminal
https://www.microsoft.com/store/productId/9N0DX20HK701
