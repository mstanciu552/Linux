- ## systemd.mount
	Mounting filesystems can be done via `systemd`. In general, the prefered approach is using `/etc/fstab`. 
	A unit configuration file whose name ends in ".mount" encodes information about a file system mount point controlled and supervised by systemd.
- ## /etc/fstab
	Filesystems, and by necessity, filesystem tables, are one of these constants. They can be a bit tricky for a lot of users, so we will look at `/etc/fstab` closer.
	`fstab` is a short version of filesystem table, and is a configuration table designed to ease the burden of mounting and unmounting file systems.

	 ### Table structure
	 The table is a 6 column structure:
	 1. **Device** - usually the given name or UUID of the mounted device(e.g. sda1)
	 2. **Mount point** - directory where the device is/will be mounted
	 3. **File system type** - type of filesystem used
	 4. **Options** - lists any active mount options
	 5. **Backup operation** - 1 = dump utility backup of partition; 0 = no backup (outdated)
	 6. **File System Check Order** - 0 = fsck will not check; numbers higher represent the check order(1 = root filesystem; 2 = other)
	  
		### Advanced use
		Existing options:
		1. auto/noauto: controls whether the partition is mounted automatically on boot(or not)
		2. exec/noexec: controls whether or not the partition can execute binaries
		3. ro/rw: controls read and write privileges
		4. nouser/user: controls whether or not the user has mounting privileges.
- ## mount
- ## Linux Unified Key Setup (LUKS)
	It is a disk encryption specification. LUKS implements a platform-independent standard on-disk format for use in various tools.
	Used to encrypt `block devices`. There is an unencrypted header at the beginning of the encrypted volume, which allows up to 8(LUKS1) or 32(LUKS2) encryption keys to be stored along with encryption parameters such as cipher type and key size.

	Using LUKS with LVM:
	1. LVM on LUKS - when LVM is used on an unlocked LUKS container, all underlying partitions can be encrypted with a single key. The LVM structure is not visible until the disk is decrypted.
	2. LUKS on LVM - When LUKS is used to encrypt LVM logical volumes, an encrypted volume can span multiple devices. The underlying LVM volume group is visible without decrypting the encrypted volume.
- ## External Devices