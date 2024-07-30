# Arch-Chroot

When I boot into an Arch Linux live USB to solve some problems, I always do the following:

- Load the layout for my keyboard:
```bash
loadkeys it
```
- Mount the root filesystem on /mnt:

```bash
mount /dev/sda3 /mnt
```

- Mount the boot filesystem on /mnt/boot:

```bash
mount /dev/sda1 /mnt/boot
```

- Mount the home filesystem on /mnt/home:

```bash
mount /dev/sda2 /mnt/home
```

Now, I ensure that my network connection works:

```bash
ping archlinux.org
```

If not, I read [this](./wireless.md).

If *pacman* still works on my system, I am ready to chroot, otherwise I must use [pacstrap](./pacstrap.md).

If both my connection to the Internet and *pacman* work, I chroot into /mnt:

```bash
arch-chroot /mnt
```
