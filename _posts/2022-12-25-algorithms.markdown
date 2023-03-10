---
layout: post
title:  "LIFO stack"
date:   2022-12-25 10:41 +0800
categories: programming
---

# Memory leak 

* heap does not have a fixed size 
* chunk of RAM -> stack and HEAP 
* heap is all the remaining memory in your computer, use malloc to get more
* malloc, -free 
* stack stores temporary variables, which each function creates as locals to that function. 
* function is pushed onto the stack and then used inside the function -> STACK data strucutre 
* local variables like char action 
* int id (in main)
* compiler pop the variables off the stack to clean up 
* if you get a block of memory from malloc, and have that pointer on the stack, then when the function exits the pointer will get popped 
* too much data on stack like large structs and arrays, then you can cause stack overflow, use heap with malloc 
* take a pointer to something on the stack, and then pass or return it from your function, then the function receiving it will segmentation fault (segfault), because the actual data will get popped off and disappear. You'll be pointing at dead space. 
* strncpy is poorly designed. fix by forcing the last character to '\0'. so that it's always set not matter what (which is what strncpy should do). 

# Pointers to Functions
Functions in C are actually just pointers to a spot in the program where some code exists. Just like you've been creating pointers to structs, string,s and arrays, you can point a pointer to a function, too. The main use for this is to pass callbacks to other functions, or to simulate classes and objects. 

int (* POINTER_NAME) (int a, int b) 

It is hard to give them as parameters to a function, such as when you want to pass the function callback to another function. The solution is to use typedef, which is a C keyword for making new names for other more complex types. 


# Available Data Types 
* int: regular integer, defaulting to 32 bits in size 
* double: holds a large floating-point number
* flaot: smaller floating-point number
* char: holds a single 1-byte char
* void: "no type" and is sued to say that a function returns nothing, or a pointer has no type, as void * thing
* enum: enumerated types, which work as and convert to integers, but give you symbolic names for sets.

# Type modifiers
* unsigned: changes the type so that it doesn't have a negative numbers, giving you a larger upper bound but nothing lower than 0. 
* signed: negative and positive numbers, but halves upper bound 
* long: larger storage for the type, hold bigger numbers 
* short: smaller storage for the type so it stores less, but takes half the space

# Type Qualifiers
* const: won't change after initialized
* volatile: all bets are off, and the compiler should leave this alone and try not to do any fancy optimizations. 
* register: forces the compiler to keep this variable in a register, and the compiler can just ignore you. 

long + char - int * double
(double) long - (double) char - (double) int * double

force it into the type you need. 

# Data Operators
-> : strucut pointer access
. : struct value access
[] : array index 
sizeof : size of a type 
&(unary): address of 
* (unary): value of 

# Linked Lists
* In c, it is possible to declare a pointer to any type. This includes pointers to structures. 
* pointers to strucutres are also used to make structures available to functions. 
* unions: aggergate data type
* it can hold members of different types 
* arrays of unions and pointer to unions are allowable. 
* -> member selection method is used with unions

union tag
{
	member list
}; 

[[C code & templates]]
* typedef storage class is used to associate an identifier with a type. 
* typedef old_type new_type; 
* typedef: processed by the compiler, only used to define data types
*  #define processed by the preprocessor, can be used to define constants, macros, and other entities as well as data types. 
* argc and argv are traditional names but can be anything 
* argc contains the count of parameters on the command line. 
* argv is an arra of poiners to chars
* the pointers point to the strings that appear on the command line 
* the array is indexed by 0 to argc -1 and terminated with a null pointer. 

# File Handling in C 
* myfile = fopen("filename", "mode"); 
* myfile = fopen("it.txt", "r"); 
* "r" - reading only
* "w" - writing only 
* "a" - open file for appending (writing at the end of file)
* "r+" - open an existing file for update (read and write)
* "w+" - create a new file for update (read and write)
* "a+" open a new or existing for read and appending 

## Formatted input and output 
printf() and scanf()
- do formated input and output to and from the terminal
fprintf() and fscanf()
- do formated input and output to and from a file
sprintf() and sscanf()
- write and read to and from a string
- more info w12 1320 

# Dynamic Allocation and De-Allocation of Memory 
- void *calloc(size_t n, size_t, size) 
- first parameter - number of items
- second parameter - size of each item 
- return value - address fo the first bte in the newly allocated buffer 
- memory allocated is initialized to 0. 
- malloc()  for performance vs calloc() initializing the memory
- malloc() does not initialize the memory it allocated 
- calloc() does initiazlie the memory it allocates

```C
#include <stdlib.h>
main(int argc, char*argv[])
{
	long int i, j, N = atoi(argv[1]);
	int a* = malloc(N*sizeof(int));
	if (a == NULL)
	{
		printf("Insufficient memory.\n"); 
		return; 
	}
}
```
# structs
- pass structs as argument to functions
```C 
float distance(struct point a, struct point b)
{
	float dx = a.x - b.x, dy = a.y-b.y; 
	return sqrt(dx*dx + dy*dy);
}
```

# Arrays
- An array is a fixed collctin of same-type data that are stored contguously and that are accessible by an index. We refer to the ith element of an array as 
```C
a[i]
```
- arrays are fundamental data structures in that they have a direct correspondence with memory system on virtually all computers. 
- we could think of the entire computer memor y as an array with the memory addresses corresponding to array indices. 
- array of characters => strings
- pointers allows us to manipulate the arrays efficiently as higher-level objects.
- we can pass a pointer to an array, so that it can access objects in the array without having to make a copy of the whole array. 
- 
# Two-dimensional array allocation
```C
int **a = malloc2d(M, N); 
//allocated an M by N array of int

int **malloc2d(int r, int c)
{
	int i;
	//each row is an array
	int **t = malloc(r*sizeof(int *));
	for (i = 0; i < r; i++)
	{
		t[i] = malloc(c*sizeof(int)); 
	}
	return t;
}
```


