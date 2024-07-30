# gentoo

> Just some notes to get going



## Kernel
Change make.conf 
ACCEPT_LICENSE=* @FREE"

```bash
$ emerge -av sys-kernel/gentoo-sources sys-kernel/linux-firmware
$ eselect kernel list
$ eselect kernel use {X}
$ eselect kernel set 1
$ cd /usr/src/linux
$ make localyesconfig
$ make -j13
$ make modules_install
$ make install
$ echo 'GRUB_PLATFORMS="efi-64"' >> /etc/portage/make.conf 
$ emerge --ask sys-boot/grub
$ grub-install --target=x86_64-efi --efi-directory=/efi
$ grub-mkconfig -o /boot/grub/grub.cfg
$ emerge --ask net-misc/dhcpcd
$ rc-update add dhcpcd default
$ rc-service dhcpcd start
$ emerge --ask sys-apps/iproute2 net-wireless/wpa_supplicant net-wireless/iw net-wireless/wireless-tools
```
