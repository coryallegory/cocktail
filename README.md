# cocktail

Trying Lubuntu 16.04.3 LTE, 32bit
https://lubuntu.net/downloads/

scratch that, going with debian, i386, 10.3.0

install with ethernet connected to internet to make life easier

username player:player

install mame
sudo apt-get install mame

https://www.mamedev.org/
https://github.com/mamedev/mame

attract-mode emulator frontend
http://attractmode.org/

sudo add-apt-repository ppa:daveg/attract
# if not found
# sudo apt-get install software-properties-common
sudo apt-get update


sudo apt-get install attract



sudo apt-get install git
libcsfml-dev



# starting over
#ubuntu server, 16.04, xenial
#install etc, connect to internet
#*x86 if older hardware, may need DD mode

#computer name arcade
#username player:play

#install mame
sudo apt-get install mame

sudo apt-get install openssh-server
sudo ufw allow ssh


sudo add-apt-repository ppa:daveg/attract
sudo apt-get update
sudo apt-get install attract

#? required:
sudo apt-get install xorg

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
