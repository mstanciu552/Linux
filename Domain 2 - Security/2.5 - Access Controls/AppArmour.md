- ## Application permissions
	1. enforce - block unwanted actions
	2. complain - report unwanted actions

	- Check information about AppArmour profiles:
		`aa-status`
	- Generate AppArmour Profile:
		`aa-genprof [path]`
	- Disable AppArmour Profile:
		`aa-disable [name]`
	- Enforce AppArmour Profile:
		`aa-enforce [name]`
	- Reading log file
		`aa-logprof`