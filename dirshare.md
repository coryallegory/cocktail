sudo apt-get install samba
sudo smbpasswd -a player
<pw play>
sudo vi /etc/samba/smb.conf:
[mame]
path = /home/player/mame
available = yes
valid users = player
read only = no
browsable = yes
public = yes
writable = yes

sudo service smbd restart


on windows:
\\<IP>\mame
