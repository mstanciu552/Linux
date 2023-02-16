- ## Basic input/output system (BIOS)
	It is **firmware** used to provide runtime services for *operating systems* and to perform *hardware initialization* during the booting process.
- ## Unified Extensible Firmware Interface (UEFI)
	It is a set of specifications written by the UEFI forum. It is an improvement over the old BIOS. Adds certain benefits sucha as:
	1. more available partitions
	2. can work with more disks
	3. supports more hardware
- ## Grand Unified Bootloader version 2 (GRUB 2)
	GNU GRUB is a **boot loader** package from the GNU Project. 
	A **boot loader** is the software that runs after the BIOS/UEFI (firmware of the motherboard) which handles connecting the kernel with the hardware.
- ## Commands
	- ### mkinitrd
		 Creates an initial image used by the kernel for preloading block devices needed to access the root filesystem (RAID, SCSI, IDE). Automatically loads modules in `/etc/modprobe`, which makes it simple to build and use kernels using modular device drivers.
		#### initrd
		Provides the capability to load a RAM disk by the bootloader. 
		1. The RAM disk can then be mounted as the root file system and programs can be run from it. 
		2. Afterwards, a new root file system can be mounted from a different device.
		3. The previous root (from `initrd`) is then moved to a directory and can be subsequently unmounted.
	- ### grub2-install
		 Script used to install `GRUB2` on a device.
		 Syntax:
			 `grub-install [OPTION...] [OPTION] [INSTALL_DEVICE]`
		 Example:
			 `grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=grub`
	- ### grub2-mkconfig
		 Scans all hard drives for installed bootable operating systems (including MacOS, Windows and Linux) and generates a GRUB2 config file.
		 The most important option is `-o/--output` which tells the program where to create the file containing the configuration. By default, output is redirected to **STDOUT**.
		 Destination for it to be found during boot:
			 `/boot/grub2/grub.cfg`
	- ### grub2-update
		 Used to replace the following command:
			 `grub2-mkconfig -o /boot/grub2/grub.cfg`
	- ### dracut
		 Used to create an initframs image by copying tools and files from an installed system and combining it with the dracut framework, usually found in `/usr/lib/dracut/modules.d`
		 Replacement of `initramfs` meant to make it faster, by having the least amount of hard-coded data in the image.
- ## initrd.img
	Initrd boot process steps:
	1. the boot loader loads the kernel and the initial RAM disks
	2. the kernel converts initrd into a *normal* RAM disk and frees the memory used by initrd
	3. if the root device is not `/dev/ram0`, the old (deprecated) **change_root** procedure is followed.
	4. root device is mounted. if it is `/dev/ram0`, the initrd image is then mounted as root 
	5. `/sbin/init` is executed (can be any valid executable); it is run with `uid 0`.
	6. init mounts the *real* root file system
	7. init places the root file system at the root directory using the *pivot_root* system call
	8. init executes the `/sbin/init` on te new root filesystem, performing the usual boot sequence
	9. the initrd file system is removed
- ## vmlinuz
	`vmlinuz` is the name of the Linux kernel executable.
	It is a compressed, bootable version of the kernel. Not to be confused with `vmlinux` which is a non-compressed, non-bootable version used in generating the `vmlinuz`.
	It is located in the `/boot` directory.
- ## Boot sources
	- ### Preboot eXecution Environment (PXE)
		 Describes a client-server environment that boots a software assembly, retrieved from a network, on PXE enabled clients. 
		 On the client side it requires only a PXE-capable NIC, and uses a small set of standard network protocols such as `DHCP` and `TFTP`.
	- ### Booting from USB
		 Loading an operating system from a USB device, containing a bootable image.
	- ### Booting from ISO
		 Loading an operating system from an image (usually stored on a USB device).