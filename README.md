# Install WSL
- Open Powershell as Administrator type: `wsl --install`
- This command will enable the required optional components, download the latest Linux kernel, set WSL 2 as your default, and install a Linux distribution for you (Ubuntu by default)

## Install other distros
- To see your options type: `wsl --list --online`
- Install one of them: `wsl --install -d <DistroName>`

## Configure WSL
- Create your account
- Update repositorys and packages:`sudo apt update && sudo apt upgrade`

## This checks the version 
- (Run this in Powershell) `wsl -l -v`

# Ubuntu GUI
- Type these to in to install required packages:  
  `sudo apt install -y xrdp`
  `sudo apt install -y xfce4`
  `sudo apt install -y xfce4-goodies`

## Config
- This command backs up our config file: `sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak`
- Port configuration, note the right one is what we will be using: `sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini`
- Controls screen scaling and color:  
  `sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini`
  `sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini`
  `echo xfce4-session > ~/.xsession`
  
## Edit
- Edit the xrdp file :  
  `sudo nano /etc/xrdp/startwm.sh`
- Comment these lines below:  
  `#test -x /etc/X11/Xsession && exec /etc/X11/Xsession`  
  `#exec /bin/sh /etc/X11/Xsession`

- Add these lines:  
  `# xfce`
  `startxfce4`

- Start RDP Service: `sudo /etc/init.d/xrdp start`

# Refrences:
- https://github.com/davidbombal/wsl2/blob/main/ubuntu_gui_youtube
- https://docs.microsoft.com/en-us/windows/wsl/install

## Intall Windows Terminal
- https://www.microsoft.com/store/productId/9N0DX20HK701
