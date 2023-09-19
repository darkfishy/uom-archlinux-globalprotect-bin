# GlobalProtect VPN Client Installer for ArchLinux

This repo contains `PKGBUILD` for Arch Linux for installing Palo Alto Network's 
GlobalProtect VPN Client app, in order to connect to 
[University of Melbourne](https://unimelb.edu.au) VPN.


This `PKGBUILD` requires the source Ubuntu installer package (`.deb`), which can 
be downloaded from [UoM VPN](https://vpn.unimelb.edu.au).

After downloading the necessary package, remember to change the relevant 
variables, such as `pkgver` and `pkgrel`. Then regenerate the checksums using:

```bash
$ makepkg -g >> PKGBUILD
```

Update the `sha256sums` appropriately.
It is also assumed that you are [building in a clean chroot](https://wiki.archlinux.org/title/DeveloperWiki:Building_in_a_clean_chroot) 
and have the [pre-requisites installed](https://wiki.archlinux.org/title/Creating_packages#Prerequisite_software).

One of the required dependencies is [qt5-webkit](https://aur.archlinux.org/packages/qt5-webkit)<sup>AUR</sup>, 
however, it takes very long to build that package. 
You may choose to install the [pre-built binary](https://aur.archlinux.org/packages/qt5-webkit#comment-896552) released 
by the current maintainer of that AUR package (FabioLolix as of 2023/09/20).
