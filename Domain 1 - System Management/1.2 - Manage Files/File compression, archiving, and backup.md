- ## gzip
	Gzip is one of the most popular compression algorithms that allow you to reduce the size of a file and keep the original file mode, ownership, and timestamp.
	Gzip also refers to the `.gz` file format which is used to compress and decompress files.

	Syntax:
		`gzip [OPTION]... [FILE]...`
	Gzip compresses only single files and creates a compressed file for each given file. 
	To compress multiple files into one file, you first need to create a `.tar` archive and then compress it with Gzip(`.tar.gz`).

	Gzip can only compress regular files, and **soft links** are ignored.

	Options:
		`gzip -k filename` -> keep the original file
		`gzip -c filename > filename.gz` -> keep original file by writing to STDOUT and redirecting to file
		`gzip -v filename`	 -> verbose output
		`gzip -r directory` -> compress all files in a given directory
		`gzip -9 filename` -> change compression level
		`gzip -d filename.gz` -> decompress (alias `gunzip`)
 - ## bzip2
- ## zip
- ## tar
- ## xz
- ## cpio
- ## dd