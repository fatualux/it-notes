# Overwrite packages

Sometimes an interrupted packages upgrading process may break several programs/libraries, and you may want to overwrite them.

If *pacman* still works on your sysstem, all you have to do is:

1. Reboot into an Arch Linux Live USB
2. Mount your disk as described [here](./arch_chroot.mda)
3. Chroot into /mnt
4. Run the following command:
```bash
sudo pacman -S $(pacman -Qnq) --overwrite "*"
```
5. Reboot into your system

The command at step 4 creates a list of all installed packages, and then reinstall them, overwriting the previous versions.
