- ## Context permissions
- ## Labels
	 - Autorelabel
- ## System booleans
- ### SELinux Pseudo-File System
	Contains commands that are most commonly used by the kernel subsystem. This type of file system is similar to the `/proc/` pseudo-file system.
- ## States
	- Enforcing
		 The SELinux security policy is enforced.
	- Permissive
		 The SELinux system prints warnings but does not enforce policy.
	- Disabled
		 The SELinux is fully disabled. SELinux hooks are disengaged from the kernel and the pseudo-file system is unregistered.
- ## Policy types
	- Targeted
		Only targeted network daemons are protected.
	- Strict
		Full SELinux protection, for all daemons. Security contexts are defined for all subjects and objects, and every action is processed by the policy enforcement server.