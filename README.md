# zfs
Backup mit Rasbperry 4
ZFS


zfs 
form d unicode normalisation
case insensitivity

diskutil list
df -h

zpool list
zpool status

diskutil partitiondisk /dev/disk3 GPTFormat ZFS %noformat% 100% 
sudo zpool create -O casesensitivity=insensitive -O normalization=formD server mirror /dev/disk1 /dev/disk2
check
zfs get all server | egrep 'compres|sensit'



sudo zpool create server mirror /dev/disk3 /dev/disk4

zpool add server mirror /Users/Tom/Desktop/disk03 /Users/Tom/Desktop/disk04


zpool detach server /dev/disk1

zpool add server raids /Users/Tom/Desktop/disk03

um von einem computer zum nächsten zu gehen:
zpool export -f server

sudo zpool import -f server
check 





tar zxvf smartmontools-6.3.tar.gz
cd smartmontools-6.3
./configure
make
sudo make install
export PATH=/usr/local/sbin:$PATH


smartctl -i /dev/disk3
smartctl -s on /dev/hdb
smartctl -H /dev/hdb 
smartctl -A /dev/hdb

seek error rates
reallocated sector count



import to another system:
sudo zpool import

sudo zpool import -f server






