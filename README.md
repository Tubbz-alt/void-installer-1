Void Linux Installer
---
Installer script as a alternative for default `void-installer`.

### FEATURES
- Automated process installation for Void Linux UEFI MUSL
- Doesn't install any Desktop Environment
- ~~Doesn't set up a common user~~
- Options for custom install in header of `install-musl.sh`
- Formating `/` with `xfs filesystem`
- With GRUB
- Enable automatically DHCP and SSH server deamons (and internet work on next reboot)

### USAGE
- Boot from Void Linux Live Image with a DE (Desktop Environment)
- Open terminal and install `git`: `sudo xbps-install -Sy git`<sup>1</sup>
- `sudo git clone http://github.com/marciliocn/void-installer`
- `cd void-installer`
- Edit the header of `install-musl.sh` to your taste
- `sudo ./install-musl.sh`
- Eject the installation media from drive and boot the machine
- ~~To enable internet after restart, run: `ln -s /etc/sv/dhcpcd /var/service/`~~
- Enjoy ;)

### INFOS
- Tested only:
	- In VirtualBox Machine
	- With UEFI MUSL
	- Arch x86_64
- <sup>1</sup> Using `void-live-x86_64-musl-20181111.iso` (without DE) in this step show "Transaction aborted due to insufficient disk space (need XXXMB, got XXMB free)". That's why use a Live Image with DE
- The version `void-live-x86_64-musl-20191109[-lxqt].iso` getting error with this installation
- The installation process running about 15 min

### TODO
- Create process installation for Void Linux BIOS/MBR MUSL
- ~~Add a pos-install script for automate tuning and another configs~~
- Add a option to choose filesystem for partitions (don't forget to change in fstab too)
- Automatic answer for import keys (on first time repository sync)
- Include `rEFInd`
- Option to install without `GRUB` (on Arch it is possible)

### CHANGELOG
#### 202001.03
- Added audio group in user creation script
- Include Uncomplicated Firewall (ufw)
#### 202001.02
- Remove TTYs from 3 to 6
- Added user and configs for sudo usage
- Adjust in /etc/rc.conf
#### 202001.01
- Added activation for DHCP and SSH server deamons
#### 201903.01
- MVP for installer, without cryptography