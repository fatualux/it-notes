# Kernel

Sometimes, after an interrupded update, your Arch Linux system may not boot.

If you got a message like this:

```bash
Loading Linux linux...
error: file '/vmzlinuz-linux' not found.
Loading initial ramdisk...
error: you need to load the kernel first.

Press any key to continue...
```

The steps you may want to follow are the following:

1. Boot into the Arch Linux Live USB
2. Mount your disk as described [here](./arch_chroot.mda)
3. Chroot into /mnt
4. Run the following commands:

    ```bash
    pacman -S linux
    mkinitcpio -p linux
    ```
5. Reboot into your system
