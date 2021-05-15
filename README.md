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
