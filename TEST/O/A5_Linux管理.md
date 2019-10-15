#
```
CompTIA® Linux+ Practice Tests
Exam XK0-004 Second Edition
```

```
Domain 1.0 Hardware and System Configuration 21% 1
1.1 Explain Linux boot process concepts
1.2 Given a scenario, install, configure, and monitor kernel modules
[重要]1.3 Given a scenario, configure and verify network connection parameters
[重要]1.4 Given a scenario, manage storage in a Linux environment
1.5 Compare and contrast cloud and virtualization concepts and technologies
1.6 Given a scenario, configure localization options
```
```
Domain 2.0 Systems Operation and Maintenance 26% 2
2.1 Given a scenario, conduct software installations, configurations, updates, and removals
2.2 Given a scenario, manage users and groups
2.3 Given a scenario, create, modify, and redirect files
2.4 Given a scenario, manage services
2.5 Summarize and explain server roles
2.6 Given a scenario, automate and schedule jobs
2.7 Explain the use and operation of Linux devices
2.8 Compare and contrast Linux graphical user interfaces
```
# Domain 1.0 Hardware and System Configuratio
```
.1 Explain Linux boot process concepts.
■■ Boot loaders such as GRUB and GRUB2
■■ Boot options such as UEFI/EFI, PXE, NFS, and booting from ISO and HTTP/FTP
■■ /etc/default/grub
■■ /etc/grub2.cfg
■■ /boot
■■ mkinitrd
■■ dracut
■■ grub2-install
■■ grub2-mkconfig
■■ initramfs
■■ linux.efi
■■ vmlinuz
■■ vmlinux

✓✓ 1.2 Given a scenario, install, configure, and monitor kernel modules
■■ lsmod
■■ insmod
■■ modprobe
■■ dmesg
■■ rmmod
■■ depmod
■■ /usr/lib/[kernelversion]
■■ /usr/lib/modules
■■ /etc/modprobe.conf
■■ /etc/modprobe.d/

✓✓ 1.3 Given a scenario, configure and verify networkconnection parameters
■■ ping
■■ netstat
■■ nslookup
■■ dig
■■ host
■■ route
■■ ip
■■ ethtool
■■ ss
■■ iwconfig
■■ nmcli
■■ brctl
■■ nmtui
■■ /etc/sysconfig/network
■■ /etc/sysconfig/network-scripts/
■■ /etc/hosts
■■ /etc/network
■■ /etc/resolv.conf
■■ /etc/netplan
■■ /etc/sysctl.conf
■■ /etc/dhcpd.conf
■■ Bonding aggregation, active/passive, load balancing

✓✓ 1.4 儲存體Given a scenario, manage storage in a Linux environment
■■ Basic partitions including raw devices, GPT, and MBR
■■ File system hierarchy including real file systems, virtual filesystems, relative paths, and absolute paths
■■ Device mappers including lvm, mdadm, and Multipath
■■ XFS tools
■■ LVM tools
■■ EXT tools
■■ fdisk
■■ parted
■■ mkfs
■■ iostat
■■ df
■■ du
■■ mount
■■ umount
■■ tune2fs
■■ fsck
■■ /etc/fstab
■■ /etc/cryptab
■■ /dev/
■■ /dev/mapper
■■ /dev/disk/by-id
■■ /etc/mtab
■■ /sys/block
■■ Filesystem types including ext3, ext4, xfs, nfs, smb, cifs, and ntfs

✓✓ 1.5 雲端與虛擬化技術Compare and contrast cloud and virtualization concepts and technologies
■■ Templates including VM, OVA, OVF, JSON, YAML, and container images
■■ Bootstrapping, including Cloud-init, Anaconda, and Kickstart
■■ Storage such as thin vs. thick provisioning, persistent volumes, blob, and block
■■ Network considerations including bridging, overlay networks, NAT, local, and dual-homed
■■ Types of hypervisors
■■ Tools such as libvirt, virsh, and vmm

✓✓ 1.6 Given a scenario, configure localization options
■■ The following is a partial list of the used files, terms, and utilities:
■■ /etc/timezone
■■ /usr/share/zoneinfo
■■ localectl
■■ timedatectl
■■ date
■■ hwclock
■■ time
■■ Environment variables such as LC_*, LC_ALL, LANG, and TZ
■■ Character sets such as UTF-8, ASCII, and Unicode
```

# Domain 2.0 Systems Operation and Maintenance
```
2.1 Given a scenario, conduct software installations,
configurations, updates, and removals
■■ Package types
■■ rpm
■■ deb
■■ tar
■■ tgz
■■ gz
■■ Installation tools
■■ RPM
■■ Dpkg
■■ APT
■■ YUM
■■ DNF
■■ Zypper
■■ Build tools
■■ Commands
■■ make
■■ make install
■■ ldd
■■ Compilers
■■ Shared libraries
■■ Acquisition commands
■■ wget
■■ curl

✓✓ 2.2 Given a scenario, manage users and groups
■■ Creation
■■ useradd
■■ groupadd
■■ Modification
■■ usermod
■■ groupmod
■■ passwd
■■ chage
■■ Deletion
■■ userdel
■■ groupdel
■■ Queries
■■ id
■■ whoami
■■ who
■■ w
■■ last
■■ Quotas
■■ User quota
■■ Group quota
■■ Profiles
■■ Bash parameters
■■ User entries
■■ .bashrc
■■ .bash_profile
■■ .profile
■■ Global entries
■■ /etc/bashrc
■■ /etc/profile.d/
■■ /etc/skel
■■ /etc/profile
■■ Important files and file contents
■■ /etc/passwd
■■ /etc/group
■■ /etc/shadow

✓✓ 2.3 Given a scenario, create, modify, and redirect files
■■ Text editors
■■ nano
■■ vi
■■ File readers
■■ grep
■■ cat
■■ tail
■■ head
■■ less
■■ more
■■ Output redirection
■■ <
■■ >
■■ |
■■ <<
■■ >>
■■ 2>
■■ &>
■■ stdin
■■ stdout
■■ stderr
■■ /dev/null
■■ /dev/tty
■■ xargs
■■ tee
■■ Here documents
■■ Text processing
■■ grep
■■ tr
■■ echo
■■ sort
■■ awk
■■ sed
■■ cut
■■ printf
■■ egrep
■■ wc
■■ paste
■■ File and directory operations
■■ touch
■■ mv
■■ cp
■■ rm
■■ scp
■■ ls
■■ rsync
■■ mkdir
■■ rmdir
■■ ln
■■ Symbolic (soft)
■■ Hard
■■ unlink
■■ inodes
■■ find
■■ locate
■■ grep
■■ which
■■ whereis
■■ diff
■■ updatedb

✓✓ 2.4 Given a scenario, manage services
■■ Systemd management
■■ Systemctl
■■ Enabled
■■ Disabled
■■ Start
■■ Stop
■■ Mask
■■ Restart
■■ Status
■■ Daemon-reload
■■ Systemd-analyze blame
■■ Unit files
■■ Directory locations
■■ Environment parameters
■■ Targets
■■ Hostnamectl
■■ Automount
■■ SysVinit
■■ chkconfig
■■ on
■■ off
■■ level
■■ Runlevels
■■ Definitions of 0–6
■■ /etc/init.d
■■ /etc/rc.d
■■ /etc/rc.local
■■ /etc/inittab
■■ Commands:
■■ runlevel
■■ telinit
■■ Service
■■ Restart
■■ Status
■■ Stop
■■ Start
■■ Reload

✓✓ 2.5 Summarize and explain server roles.
■■ NTP
■■ SSH
■■ Web
■■ Certificate authority
■■ Name server
■■ DHCP
■■ SNMP
■■ File servers
■■ Authentication server
■■ Proxy
■■ Logging
■■ Containers
■■ VPN
■■ Monitoring
■■ Database
■■ Print server
■■ Mail server
■■ Load balancer
■■ Clustering

✓✓ 2.6 Given a scenario, automate and schedule jobs
■■ cron
■■ at
■■ crontab
■■ fg
■■ bg
■■ &
■■ kill
■■ Ctrl+C
■■ Ctrl+Z
■■ nohup

✓✓ 2.7 Explain the use and operation of Linux devices
■■ Types of devices
■■ Client devices
■■ Bluetooth
■■ WiFi
■■ USB
■■ Monitors
■■ GPIO
■■ Network adapters
■■ PCI
■■ HBA
■■ SATA
■■ SCSI
■■ Printers
■■ Video
■■ Audio
■■ Monitoring and configuration tools
■■ lsdev
■■ lsusb
■■ lspci
■■ lsblk
■■ dmesg
■■ lpr
■■ lpq
■■ abrt
■■ CUPS
■■ udevadm
■■ add
■■ reload-rules
■■ control
■■ trigger
■■ File locations
■■ /proc
■■ /sys
■■ /dev
■■ /dev/mapper
■■ /etc/X11
■■ Hot pluggable devices
■■ /etc/rc5/udev
■■ /etc/udev/rules.d


✓✓ 2.8 Compare and contrast Linux graphical user interfaces
■■ Servers
■■ Wayland
■■ X11
■■ GUI
■■ Gnome
■■ Unity
■■ Cinnamon
■■ MATE
■■ KDE
■■ Remote desktop
■■ VNC
■■ XRDP
■■ NX
■■ Spice
■■ Console redirection
■■ SSH port forwarding
■■ Local
■■ Remote
■■ X11 forwarding
■■ VNC
■■ Accessibility
```
