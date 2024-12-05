## Unpack first
    $ sudo unmkinitramfs /path/to/initramfs.img /path/to/extracted-directory


## Pack it (i think its wrong)
    $ sudo mkinitramfs -o /path/to/new-initramfs.img kernel-version

### this one should work:
    $ cd /path/to/modified-initramfs
    $ find . | cpio -o -H newc | gzip > /boot/new-initramfs.gz




## Interrupt the Boot at GRUB:

When GRUB appears, press a key (usually <kbd>Esc</kbd> or <kbd>Shift</kbd>) to interrupt the countdown and enter the GRUB menu

#### Edit the Boot Entry:

Highlight the kernel you want to boot and press <kbd>e</kbd> to edit the boot entry.
Look for a line starting with `initrd`, which specifies the initramfs file.
Replace the default initramfs path (e.g., initrd.img-<version>) with your new one:

    $ initrd /boot/my_raminitfs.gz

Do not modify the kernel line or the root filesystem line.
Press <kbd>Ctrl</kbd>+<kbd>X</kbd> or <kbd>F10</kbd> to boot with the modified settings.

[unpacking](https://linuxconfig.org/how-to-uncompress-and-list-an-initramfs-content-on-linux)
