- ### Process States
	- Running -> R
	- Stopped -> T
		 Process that is pused and in the background.
	- Sleeping -> S/D
		 2 states:
		- Interruptable -> S
			Can still send signals and accepts them.
		- UnInt -> D
			 
	- Zombie -> Z
		 When a process spawns a *child* process and said process stops running, but the parent does not clean up after the child and a PID remains even though the process stopped, the *child* process is called a **zombie process**. 