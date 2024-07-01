# Pacstrap

**Pacstrap** is used to create a new system installation from scratch.
Unlike *pacman*, it does not require the -S flag, but it requires a target directory to be specified for the installation.

## Usage

```bash
pacstrap [options] root [packages...]
```

| Command | Description |
| --- | --- |
| `pacstrap` | Install packages to the specified new root directory. |
| `pacstrap -i` | Install packages to the specified new root directory and run interactively. |
| `pacstrap -N` | Install packages to the specified new root directory in unshare mode. |

Run ```man pacstrap``` for more information.
