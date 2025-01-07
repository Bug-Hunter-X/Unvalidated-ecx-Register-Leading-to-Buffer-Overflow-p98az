# Unvalidated ecx Register Leading to Buffer Overflow in Assembly

This repository demonstrates a common error in assembly programming:  unvalidated register use leading to a buffer overflow vulnerability. The `bug.asm` file contains the vulnerable code, while `bugSolution.asm` provides a corrected version.

The vulnerability arises from the lack of bounds checking on the `ecx` register before accessing memory using the address calculation `ebx + ecx * 4`.  This allows an attacker to manipulate `ecx` to access memory outside the allocated bounds, potentially resulting in a segmentation fault, arbitrary code execution, or other unpredictable behavior. 

The solution involves adding a check to ensure that the calculated address falls within the allowed memory region before accessing it.