[Documentation](https://ostechnix.com/explaining-soft-link-and-hard-link-in-linux-with-examples/)
- ## Soft Links
	Soft links or **symbolic links** are actually a link to the original file, meaning they point to that file and do not actually copy it.
	If the original file is deleted, the link will be useless since it now points to nothing.
 
	Syntax:
		`ln -s <source> <destination>`
  
	Properties:
	1. can cross the filesystem
	2. allows you to link between directories
	3. has different inode number and file permissions than the original file
	4. permissions will not be updated
	5. has only the path of the original file, not the contents
- ## Hard Links
	Hard links are a mirror copy of the original file. Even if the original file is deleted, the hard link still has all the data of the original.

	Syntax:
		`ln <source> <destination>`

	Properties:
	1. can't cross the filesystem boundries(i.e. A hard link can only work on the same filesystem)
	2. can't link directories
	3. has the same inode number and permissions of the original file
	4. permissions will be updated if we change the permissions of the source file
	5. has the actual contents of the original file, so that you can still view the contents, even if the original file was moved or removed
 
	Difference between **hard link** and **copied file**:
	1.  A hard link and its original file will both be changed to match each other, meaning if we modify the hard link the original file will be modified, and if we modify the original file the hard link will be modified
	2. A copied file only copies the contents of the original file and nothing else. So if the copy is changed the original file will not reflect those changes.
 
	