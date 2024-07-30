# Partitioning

I prefer to keep my /boot/ and my /home/ directories on separate partitions.
This way, when the disaster happens, I can destroy all the system directories, keeping my data and custom configs safe in separate partitions.

I have also a local backup of my data and configs, and I try to keep updating the most important dotfiles of mine in a git repository.

This is my partitioning scheme:

```bash
[fz@fzpc ~]$ fdisk -l # list all devices

Disk /dev/sda: 698,64 GiB, 750156374016 bytes, 1465149168 sectors
Disk model: WDC WD7500BPKT-0
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 4096 bytes
I/O size (minimum/optimal): 4096 bytes / 4096 bytes
Disklabel type: dos
Disk identifier: 0x000b7bec

Device     Boot     Start        End    Sectors   Size Id Type
/dev/sda1  *         2048    1230847    1228800   600M  b W95 FAT32
/dev/sda2         1230848   66766847   65536000  31,3G 82 Linux swap / Solaris
/dev/sda3        66766848  224053247  157286400    75G 83 Linux
/dev/sda4       224053248 1465149167 1241095920 591,8G 83 Linux
```
|Device|Partition|
|---|---|
|`sda1`|`/boot`|
|`sda2`|`swap`|
|`sda3`|`/`|
|`sda4`|`/home`|
