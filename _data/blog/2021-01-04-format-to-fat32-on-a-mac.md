---
template: BlogPost
path: /how-to-format-an-sd-card-to-fat32-on-a-mac-without-a-virtual-machine
date: 2020-07-06T01:24:00.000Z
title: Format to FAT32 on a mac
thumbnail: /assets/drive.png
---
If you have a need to format your SD card to FAT32, in my case following trying to flash [OpenIP](https://github.com/openipcamera/openipc-firmware) to WYZE camera, you can do it right from your mac.

We will use Disk Utility command line interface to achieve this. To get started, open a terminal window.

Find out the disk number for your SD card.

```
diskutil list
```

This should give you something like the following.

```
/dev/disk0 (internal, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *500.3 GB   disk0
   1:                        EFI EFI                     209.7 MB   disk0s1
   2:                 Apple_APFS Container disk1         452.4 GB   disk0s2
   3:       Apple_KernelCoreDump                         655.4 MB   disk0s3
   4:       Microsoft Basic Data OSXRESERVED             8.0 GB     disk0s4
   5:           Windows Recovery                         471.9 MB   disk0s5
   6:                        EFI NO NAME                 104.9 MB   disk0s6
   7:         Microsoft Reserved                         16.8 MB    disk0s7
   8:                  Apple_HFS Free                    38.3 GB    disk0s8

/dev/disk1 (synthesized):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      APFS Container Scheme -                      +452.4 GB   disk1
                                 Physical Store disk0s2
   1:                APFS Volume Macintosh HD            377.9 GB   disk1s1
   2:                APFS Volume Preboot                 54.3 MB    disk1s2
   3:                APFS Volume Recovery                517.1 MB   disk1s3
   4:                APFS Volume VM                      2.1 GB     disk1s4

/dev/disk3 (external, physical):
   #:                       TYPE NAME                    SIZE       IDENTIFIER
   0:      GUID_partition_scheme                        *31.3 GB    disk3
   1:         Microsoft Reserved                         33.6 MB    disk3s1
   2:           Linux Filesystem                         25.2 MB    disk3s2
   3:           Linux Filesystem                         268.4 MB   disk3s3
   4:           Linux Filesystem                         25.2 MB    disk3s4
   5:           Linux Filesystem                         268.4 MB   disk3s5
   6:           Linux Filesystem                         8.4 MB     disk3s6
   7:           Linux Filesystem                         100.7 MB   disk3s7
   8:           Linux Filesystem                         30.5 GB    disk3s8
```

You need to look for the SD card size and name if it's already formatted. In this case, `disk3` is what we are looking for.

Simply running the following will format it to FAT32.

`sudo diskutil eraseDisk FAT32 'VOL_NAME' disk3`

⚠️ The volume name must be all caps otherwise you will see `error: does not appear to be a valid volume name for its file system`.

You should now have an SD card with FAT32 formatting.
