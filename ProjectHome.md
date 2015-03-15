A small piece of [shellcode](http://skypher.com/wiki/index.php/Hacking/Shellcode) written in assembler that can scan the user-land address space for small blocks of memory ("eggs") and recombine the eggs into one large block. When done, the large block is executed. This is useful when you can only insert small blocks at random locations into a process and not one
contiguous large block containing your shellcode in one piece: this code will recombine the eggs to create your shellcode in the process and execute it.

This version works only on Windows 32-bit platforms because it uses the Windows specific Structured Exception Handler ([SEH](http://skypher.com/wiki/index.php/Hacking/Windows_internals/Process/SEH)) feature to handle access violations caused by scanning memory.

For more information, have a look at [this wiki page](http://skypher.com/wiki/index.php?title=Hacking/Shellcode/Egg_hunt/w32_SEH_omelet_shellcode).

**NOTE** It seems that the code does not always work. The root cause of the problem is unknown, more information and a potential fix can be found [here](http://www.corelan.be:8800/index.php/2010/01/09/exploit-writing-tutorial-part-8-win32-egg-hunting/).