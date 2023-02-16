- ## /boot
	Boot loader files (`kernels`, `initrd`).
- ## /proc
	Virtual filesystem providing process and kernel information as files.
- ## /sys
	Contains information about devices, drivers, and some kernel features.
- ## /var
	Variable files: files whose content is expected to continually change during normal operation of the system, such as logs, spool files, and temporary e-mail files.
- ## /usr
	Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications. Should be shareable and read-only.
- ## /lib
	Libraries essential for the binaries in `/bin` and `/sbin`.
- ## /dev
	Device files (`/dev/null`, `/dev/zero`, `/dev/random`, `/dev/sda1`).
- ## /etc
	System wide configuration files.
- ## /opt
	Add-on application software packages.
- ## /bin
	Essential command binaries that need to be available in single-user mode, including to bring up the system or repair it, for all users (`cat`, `ls`, `cp`).
- ## /sbin
	Essential system binaries (`fsck`, `init`, `route`).
- ## /home
	User home directories.
- ## /media
	Mount points for removable media such as CD-ROMs.
- ## /mnt
	Temporarily mounted filesystems.
- ## /root
	Home directory for the root user.
- ## /tmp
	Directory for temporary files (see also `/var/tmp`). Often not preserved between system reboots and may be severely size-restricted.
