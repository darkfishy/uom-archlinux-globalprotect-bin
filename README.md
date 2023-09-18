# GlobalProtect VPN Client Installer for ArchLinux

This repo contains `PKGBUILD` for installing Palo Alto Network's GlobalProtect
VPN Client app, distributed by [University of Melbourne](https://unimelb.edu.au),
on Arch Linux, in order to connect to UoM VPN.

This `PKGBUILD` requires the source Ubuntu installer package (`.deb`), which can 
be downloaded from [UoM VPN](https://vpn.unimelb.edu.au).

After downloading the necessary package, remember to change the relevant 
variables, such as `pkgver` and `pkgrel`. Then regenerate the checksums using:

```bash
$ makepkg -g >> PKGBUILD
```

Update the `sha256sums` appropriately.
