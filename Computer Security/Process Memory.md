[Anatomy of a Program in Memory](https://manybutfinite.com/post/anatomy-of-a-program-in-memory/)
- This models process memory with kernel space and the stack at the "top" and code at the "bottom", which is the reverse of the way I like to think of it

Address space is 64-bit, starting from 0 and going up to $2^{64}$

From smallest memory address to largest memory address
- Code (aka text)
	- Program Counter points to memory address of next instruction to be executed
- Static data (i.e. global variables)
	- Space reserved for static variables initialised in source code
	- Maps to program's binary image containing initial static values from source code
	- **BUT** it is a **private memory mapping**, i.e. changes to static variables do not get updated back to the original binary image (lol)
- Block starting symbol (BSS) segment
	- Space reserved for *uninitialised* static variables
- Heap
- Memory Mapping Segment, used for two things;
	- [Memory-mapped files](https://en.wikipedia.org/wiki/Memory-mapped_file)
	- `malloc` requests larger than `MMAP_THRESHOLD` bytes (128 kB by default)
- Stack
	- Stack Pointer points to memory address of top of stack
	- If stack overlaps with heap: stack overflow
- Kernel space

## Address space randomisation
- Adds a random offset to the starting address of:
	- Heap
	- Memory mapping segment
	- Stack
- Reduces the chance that an attacker can guess where a piece of data or code is stored in memory