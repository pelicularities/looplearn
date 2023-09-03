Something is **static** if we know exactly how much space it will take up at runtime:
- program code is static: number of instructions (and therefore amount of memory) required by program code does not change once loaded into memory
- global variables are static: they are never garbage collected or freed
	- `static` keyword tells compiler: always reserve space for this variable
- heap variables are not static: amount of memory required by variables on the heap changes as variables are allocated/freed/garbage collected
- stack is not static: stuff is constantly pushed onto and popped off the stack

## Why virtualise memory?
## How to virtualise memory?
## Every address you see is virtual
- Only the OS really knows the physical memory address!