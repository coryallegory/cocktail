# cocktail

## Setup Instructions

1. Install Lubuntu 16.04 (Xenial) LTE, i386
  - Download from https://lubuntu.net/downloads/
  - Burn iso to USB (may need DD mode), and boot device
  - May need to use a Plop bootcd if USB boot isn't natively supported
  - Ensure ethernet connectivity to make installing easier
  - Use machine particulars:
    - system name: arcade
    - user/password: player/play

1. Enable SSH if not done during install
  - sudo apt-get install openssh-server
  - sudo ufw allow ssh

1. Install Mame
  - https://www.mamedev.org/
  - https://github.com/mamedev/mame
  - 
  - sudo apt-get update
  - sudo apt-get install mame -y

1. Install Attract front end
  - http://attractmode.org/
  - 
  - sudo add-apt-repository ppa:daveg/attract
  - sudo apt-get update
  - sudo apt-get install attract


sudo apt-get install git


#? required if running ubuntu server:
sudo apt-get install xorg-dev

echo "exec attract" > ~/.xinitrc
startx


#attract mode will start unconfigured


#start at boot
put startx command in
/etc/rc.local
to run at boot time



sudo apt-get install unzip

roms go into ~/mame/roms/
global config /etc/mame/mame.ini
user config ~/.mame/mame.ini
