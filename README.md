## Samba config example

```
[BigBittorentDownloads]
path = /media/bigdata/BigBittorentDownloads
writeable = yes
browseable = yes
create mask = 0777
directory mask = 0777
public = no

[BittorentDownloads]
path = /media/data/dowload
writeable = yes
browseable = yes
create mask = 0777
directory mask = 0777
public = no
```

## Auto-mounting an external drive via fstab

`sudo blkid` to get UUID of the disk partition

`sudo vim /etc/fstab`

add the lines to fstab:

`UUID={uuid from blkid} /mnt/exdisk fstype defaults,auto,users,rw,nofail 0 0`

test with `sudo mount -a`

Example of how it looks after a successful setup on rpi

```
UUID=d1ed68e6-e2c1-4f8f-85a3-a3f3a0f65241 /media/bigdata ext4 defaults,auto,users,rw,nofail 0 0
UUID=a0b07a58-7176-4b72-b24f-ae02cf72b9c6 /media/data ext4 defaults,auto,users,rw,nofail 0 0
```
