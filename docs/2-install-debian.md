# Install Debian 11.7 on HP T-620

1. Download `Debian` [image](https://www.debian.org/download)
2. Flash image into USB stick by balenaEtcher
3. Run terminal and press ESC. Wait for BIOS
4. Press F10 and go to Storage -> Boot Order
5. Choose USB as UEFI 1st option to boot
6. Restart terminal
7. Follow installing instructions
8. If installation ready, then remove USB stick and restart terminal.
9. If want to use Debian with graphical interface, then by default it won't boot from UEFI.
10. Go [here](http://www.rodsbooks.com/refind/getting.html) and download QeEFInd.
11 .Flash it to USB and insert into terminal
12. login to Debian and change to root:
```
su
```
13. Then execute commands:
```
mkdir /boot/efi/EFI/boot
cp /boot/efi/EFI/debian/grubx64.efi /boot/efi/EFI/boot/bootx64.efi
systemctl reboot
```
14. Go to BIOS F10 and allow booting only from Debian UEFI.
15. If graphical interface is not necessary, then steps from 9 can be omitted.

## Enable auto start after power off
BIOS F10
Advanced -> Power-On Options -> After Power Loss/AC Back Function/Restore AC Power Loss -> On 

## Update Distro
```
su
apt update
apt upgrade
```

## Install sudo
```
su -
apt install sudo
usermod -aG sudo <username>
exit
```

Relogin and check if sudo works for user

## Install openssh-server
```
sudo apt install openssh-server -y
ip a
```