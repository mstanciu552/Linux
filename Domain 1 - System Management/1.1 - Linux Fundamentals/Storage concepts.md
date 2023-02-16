- ### File storage
	Offers to multiple clients access to a shared filesystem.
	Examples are: NFS, CIFS, SMB.
- ### Block storage
	Offers access to block devices. Usually not to multiple clients.
	Can be used as local block devices (can be booted from).
- ### Object storage
	Simple and new. Stores unstructured data(photos, logs, backups) as key/value pairs.
	Example: AWS S3.
- ### Partition type
	- Master Boot Record (MBR)
		 It is a special type of *boot sector* at the very beginning of partitioned computer mass storage devices like fixed disks or removable drives intended for use with IBM PC-compatible systems and beyond.
		 Is older and has size limitations: max 2 TiB.
	- GUID (Globally Unique Identifier) Partition Table
		 Improvement over MBR. Does not share MBR's limitations of size.
		 Was developed to replace MBR.
- ### Filesystem in Userspace (FUSE)
	The rationale of implementing a Filesystem in userspace apart from giving you more control over the file operations , it also allows you to achieve more portability without implementing a kernel module and can easily be ported even via containerization mechanisms. Also a bug wont bring the kernel down as this is completely a userspace implementation.	
- ### Redundant Array of Independent (or Inexpensive) Disks (RAID) levels
	Method of preventing data loss. There are 4 levels to RAID:
	1. Raid 0 - **Striping**
		Not Fault Tolerant
		Data not duplicated, but spread across disks. If one disk fails, all disks fail.
		Its advantage is **speed**.
	2. Raid 1 - **Mirroring**
		Fault tolerant
		Data is duplicated (mirrored) on multiple disks. If one disk fails, all data is still safe.
	3. Raid 5 - **Striping with parity**
		Requires 3 or more disks.
		Data is not duplicated, but spread across multiple disks.
		Parity is evenly distributed. Used to rebuild the data in case of disk failure.
		Reduces amount of space available (parity occupies a lot of space).
	4. Raid 10 - 1 + 0 => **Striping + Mirroring**
		Minimum of 4 disks.
		Parity between pairs of disks.
		Only 50% of storage available.