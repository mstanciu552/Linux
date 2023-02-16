- ### Block devices
	Reads to and writes to a device in a block of different sizes.
	Usually storage hardware: HDD, SSD, etc.
- ### Character devices
	Sends bytes to hardware sequentially(one character=one byte at a time).
- ### Special character devices
	- **/dev/null**
		Device that does not use **STDOUT**.
		Anything that is sent inside never comes out.
	- **/dev/zero**
		Outputs zeroes(0), not as ASCII, but as bits.
	- **/dev/urandom**
		Generates random numbers.