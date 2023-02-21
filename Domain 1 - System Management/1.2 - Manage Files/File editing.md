- ## sed
	Stands for `Stream Editor`.
	Syntax:
		`sed OPTIONS... [SCRIPT] [INPUTFILE...]`
	Example:
		`sed 's/<search>/<replace>/2' file.txt`
	Options:
		`-e <script>/--expression=<script>`
		`-f <script-file>/--file=<script>`
		`-r <regex>/--regexp-extended`
- ## awk
	Programming language for text manipulation.
	Works with STDIN and files.
	Syntax:
		`awk '{print $1}' file.txt`
		`cat file.txt | awk '{print $1}'`
	Examples:
	```
		1:file2:98
		2:file:100
		3:file3:78
	```
	`awk -F ":" '{print $2}' file.txt`

- ## printf
	Bash shell builtin used to make output more readable.
	Similar to printf in C programming language.