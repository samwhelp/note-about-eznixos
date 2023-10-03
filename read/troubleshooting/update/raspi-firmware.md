---
title: raspi-firmware
nav_order: 8011
has_children: false
parent: Update
grand_parent: Troubleshooting
---


# raspi-firmware

## Issue

when update linux-image-amd64


## 探索

執行

``` sh
dpkg -L raspi-firmware
```

顯示

```
/.
/etc
/etc/default
/etc/default/raspi-firmware
/etc/initramfs
/etc/initramfs/post-update.d
/etc/initramfs/post-update.d/z50-raspi-firmware
/etc/kernel
/etc/kernel/postinst.d
/etc/kernel/postinst.d/z50-raspi-firmware
/etc/kernel/postrm.d
/etc/kernel/postrm.d/z50-raspi-firmware
/lib
/lib/firmware
/lib/firmware/brcm
/lib/firmware/brcm/brcmfmac43430-sdio.txt
/lib/firmware/brcm/brcmfmac43455-sdio.txt
/lib/firmware/brcm/brcmfmac43456-sdio.bin
/lib/firmware/brcm/brcmfmac43456-sdio.clm_blob
/lib/firmware/brcm/brcmfmac43456-sdio.txt
/usr
/usr/lib
/usr/lib/raspi-firmware
/usr/lib/raspi-firmware/bootcode.bin
/usr/lib/raspi-firmware/fixup.dat
/usr/lib/raspi-firmware/fixup4.dat
/usr/lib/raspi-firmware/fixup4cd.dat
/usr/lib/raspi-firmware/fixup4db.dat
/usr/lib/raspi-firmware/fixup4x.dat
/usr/lib/raspi-firmware/fixup_cd.dat
/usr/lib/raspi-firmware/fixup_db.dat
/usr/lib/raspi-firmware/fixup_x.dat
/usr/lib/raspi-firmware/start.elf
/usr/lib/raspi-firmware/start4.elf
/usr/lib/raspi-firmware/start4cd.elf
/usr/lib/raspi-firmware/start4db.elf
/usr/lib/raspi-firmware/start4x.elf
/usr/lib/raspi-firmware/start_cd.elf
/usr/lib/raspi-firmware/start_db.elf
/usr/lib/raspi-firmware/start_x.elf
/usr/share
/usr/share/doc
/usr/share/doc/raspi-firmware
/usr/share/doc/raspi-firmware/changelog.Debian.gz
/usr/share/doc/raspi-firmware/copyright
/usr/share/initramfs-tools
/usr/share/initramfs-tools/hooks
/usr/share/initramfs-tools/hooks/raspi-firmware-fsck
/usr/share/lintian
/usr/share/lintian/overrides
/usr/share/lintian/overrides/raspi-firmware
```


## Howto

remove file first

``` sh
sudo rm -f /etc/initramfs/post-update.d/z50-raspi-firmware
sudo rm -f /etc/kernel/postinst.d/z50-raspi-firmware
sudo rm -f /etc/kernel/postrm.d/z50-raspi-firmware
```

then remove package

``` sh
sudo apt-get purge raspi-firmware
```

