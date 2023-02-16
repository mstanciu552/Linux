- ### lspci
	Utility used to get information about PCI devices(e.g. Graphics Cards, Network Cards)
- ### lsusb
	Utility used to get information about USB devices(e.g. Keyboard, Mouse, Stick)
- ### dmidecode
	Utility used to dump a computer's DMI table contents to a human-readable format. Contains a description of the system's hardware components, as well as other useful information such as Serial Numbers and BIOS revision.
	
	As you run it, dmidecode will try to locate the DMI table. If it succeeds, it will then parse this table and display a list of records like this one:

		Handle 0x0002, DMI type 2, 8 bytes. Base Board Information Manufacturer: Intel
		Product Name: C440GX+
		Version: 727281-001
		Serial Number: INCY92700942
	
	Each record has:
	
	1. **A handle**. This is a unique identifier, which allows records to reference each other. For example, processor records usually reference cache memory records using their handles.
	2. **A type**. The SMBIOS specification defines different types of elements a computer can be made of. In this example, the type is 2, which means that the record contains "Base Board Information".
	3. **A size**. Each record has a 4-byte header (2 for the handle, 1 for the type, 1 for the size), the rest is used by the record data. This value doesn't take text strings into account (these are placed at the end of the record), so the actual length of the record may be (and is often) greater than the displayed value.
	4. **Decoded values**. The information presented of course depends on the type of record. Here, we learn about the board's manufacturer, model, version and serial number.