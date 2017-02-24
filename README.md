# Buffer Overflow exploit:

Using the buffer overflow vulnerability in auth, implement the following:

   1. A simple stack smashing attack that executes injected code on the stack that calls ownme(). 
	  First do this by redefining RANDOM to be 0 in the Makefile. Once that works, try to revert 
	  it back to random() and see if you can compensate using a NOP-sled.

	  For all of the following parts, define RANDOM=0 in the Makefile.
	
   2. Use stack smashing to modify saved BP value on the stack frame of auth so that when control 
	  returns to g, you have control of the local variables of g, and can use this to set s2 to 
	  /bin/bash even when auth returns 0.

   3. Use a return-to-libc attack that calls execl (or another function with a similar functionality) 
      in libc, the standard C library. You should control the arguments so that you get a shell.

   4. Use a data-only-attack on the local variable authd. In particular, use stack smashing in auth to 
      go past the stack frame of auth into its caller’s frame, and modify the value of authd there.