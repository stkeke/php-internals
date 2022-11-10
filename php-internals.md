[]
# Q: What is the use of ```zend_arena *arena;``` in ```zend_globals.h::_zend_compiler_globals{}```?
To answer this question, let's first understand data structure ```zend_arena{}```, which is defined in ```zend_arena.h``` as below:
```c
typedef struct _zend_arena zend_arena;

struct _zend_arena {
	char		*ptr;
	char		*end;
	zend_arena  *prev;
};
```
We can see that there are three member in the structure: 
1. ```ptr``` points to the start address of a memory area;
2. ```end``` points to the end address of the memory area;
3. ```prev``` points to the previous structure of ```zend_arena```, and in this way, structures of ```zend_arena``` forms a linked list like below.



Some functions are also defined in ```zend_arena.h``` and they are used to manage 

