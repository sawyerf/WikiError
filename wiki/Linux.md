# Linux

- [Discord](#discord)
- [Grub](#grub)
- [Git](#git)
- [General](#general)
- [Locale](#locale)
- [Python](#python)
- [Xorg](#xorg)
- [Youtube-dl](#youtube-dl)

## Grub
### vmlinuz not found after update (2020/02/22)
Error Message:
```
error: file `/boot/vmlinuz-5.2-x86_64` not found
error: you need to load the kernel first
```
Solution:
```bash
sudo mkinitcpio -P
```
- Source: https://forum.manjaro.org/t/howto-rescue-your-system-error-hook-invalid-value-path/123226

### Change default boot
1. Backup `/etc/default/grub`:
```bash
sudo cp /etc/default/grub /etc/default/grub.bak
```
2. Edit Variable `GRUB_DEFAULT` in `/etc/default/grub`: 
```bash
GRUB_DEFAULT=0
```
3. Update Grub
```bash
sudo update-grub
```
- Source: https://linuxhint.com/change-grub-options/

## Discord
### Discord dosn't detect microphone
Solution:
- Install pulse

## Youtube-dl
### Broken .part (`moov atom not found`)
Solution:
```
untrunc working_file.mp4 broken_file.mp4.part
```

## Xorg
### Change display setting with command
Solution:
```
$ nvidia-settings -q CurrentMetaMode

Attribute 'CurrentMetaMode' (hostnmae:0.0): id=50, switchable=no, source=nv-control :: DPY-1: 2880x1620 @2880x1620 +0+0 {ViewPortIn=2880x1620, ViewPortOut=2880x1620+0+0}
```
Save everything after the :: to the end of the attribute (in this case: DPY-1: 2880x1620 @2880x1620 +0+0 {ViewPortIn=2880x1620, ViewPortOut=2880x1620+0+0}) and use to reconfigure your displays with `nvidia-settings --assign "CurrentMetaMode=your_meta_mode"`.
[source](https://wiki.archlinux.org/index.php/NVIDIA#Using_nvidia-settings)

## General
### Mount a Partition at boot
Get UUID with the command:
```
sudo blkid
```
Edit the file `/etc/fstab` and add:
```
UUID=<UUID>                      <Path>        <System File>   defaults,noatime 0 0
```

### Suspend when close the laptop
Edit `/etc/systemd/logind.conf` and reboot:
```
HandleLidSwitch=ignore
```

### Create a Bootable USB for Windows
Use **Woeusb**

## Python
### Slow PIP3
Disable ipv6
```
sudo sysctl -w net.ipv6.conf.all.disable_ipv6=1
sudo sysctl -w net.ipv6.conf.default.disable_ipv6=1
```

## Locale
### Unsupported locale setting
Edit `/etc/locale.gen` and uncomment a line
and execute:
```
locale-gen
```

## Git
### Edit commit author
#### Last commit
```
git commit --amend --author="Sawyerf <sawyer.flink@protonmail.ch>"
```

Source:
- https://www.git-tower.com/learn/git/faq/change-author-name-email/

# Dualboot
## Date problem
```bash
sudo timedatectl set-local-rtc 1 --adjust-system-clock
```
