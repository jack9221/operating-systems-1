# operating systems 1
## Interrupt Based Systems
Modern Operating Systems are mostly interrupt based systems <br>
During booting, the ROM (Read-only Memory) calls the OS from the hard disk to the memory <br>
After booting, the operating system resides in memory and waits for I/O events. <br>
Your operating system displays a bunch of files and applications as well as a cursor which you are familiar with. <br>
As soon as you move your mouse, it sends an interrupt to the CPU, forcing the CPU to stop its current task and jump to the mouse interrupt service routine provided by your operating system <br>
The mouse interrupt service routine provides a set of instructions for how to display your mouse on the screen. <br>
Lets say you clicked on a microsoft word document. This again sends an interrupt to the CPU and the CPU halts its current task and moves to the corresponding interrupt service routine provided by the OS. Then it loads the application from the hard disk to the main memory. <br>
Softwares can call interrupts too!
<br><br>

Imagine a program that needs to access a .doc file. It does not have the capability to do so by itself and needs to call the operating system (which has the appropriate service routine) for help. Thus it calls the software interrupt which directs the CPU to the operating system. After the .doc file is read with the OS' help, the CPU goes back to the program and executes the ramaining lines of code.

There are mainly three ways to cause an interrupt.
1. Hardware Interrupt -> Clicking on a mouse, entering on a keyboard...
2. Software Interrupt -> Software needs access to input from the user, software needs to access the hard disk...
3. System Interrupt -> There is a divide by 0 error in the program so the program needs to exit with a warning/error...

When CPU executes command from OS it is in supervisor mode, when it executes command from program files it is in user mode.
This is to prevent user for security and reliability purposes as you can probably tell.
So how can the CPU know whether it should be in supervisor mode or user mode?
There is a bit in the CPU register ( 1 - system mode, 0 - user mode )
These two modes act as a layer of protection... if the user tries to run privileged commands in user mode, this causes an interrupt to the processor which calls the operating system, which runs the interrupt service routine, which exits the program and throws it out of the memory stack.
