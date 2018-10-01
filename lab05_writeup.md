Bhav Singh 
EE250 
Riot Lab5 


Question 1: 

question_1_screenshot.png is provided

Question 2:  

Briefly explain what the text segment, bss segment, and data segment of compiled code consists of in your lab05_writeup.md. Write a few sentences for each. You may need to google this

Resources
{
	https://github.com/RIOT-OS/RIOT/wiki/FAQ
	https://en.wikipedia.org/wiki/.bss
	https://www.geeksforgeeks.org/memory-layout-of-c-program/

}

This depends on the board and on the application. When you compile an application for a board, the last thing printed gives each sections memory footprint and looks like this:

data     bss     dec     hex filename
  77732     296   24272  102300    18f9c applications/sixlowapp/bin/iot-lab_M3/sixlowapp.elf

the memory footprint sections are split into bss, data, and dec. You can get the 
required ram by data + bss. And you can get the rom by text + data. 

data: the data segment contains initialized static variables, global variables, and static local variables. 
The size does not change at run time and is dependent upon the size of the variables that are stored in the 
segment. This segment can be further classified into initialized read-only area and initialized read-write area. 

bss: typically only the length of the bss section, no data, is stored in the object file. The program loader
allocates memory for the bss section when it loads the program. It contains statically-allocated variables 
that are not explicitly initialized to any value.

For instance a variable declared static int i; would be contained in the BSS segment.
For instance a global variable declared int j; would be contained in the BSS segment.

text: 

A text segment , also known as a code segment or simply as text, is one of the sections of a program in an object file or in memory, which contains executable instructions. As a memory region, a text segment may be placed below the heap or stack in order to prevent heaps and stack overflows from overwriting it. Also, the text segment is often read-only, to prevent a program from accidentally modifying its instructions.

Question 3: 

In main.c of the hello-world example, the RIOT_BOARD and RIOT_MCU are used but not explicitly defined in the file. In C, we define macros using `#define`. Make can do the same by prepending the `-D` flag. Use your text editor (e.g. ctrl+shift+f in Sublime Text) to search the entire codebase under the RIOT base directory for the specific file named `Makefile.include` that defines RIOT_BOARD and RIOT_MCU. What is the relative path to the file?

RIOT-EE250/Makefile.include

Question 4:

question_4_screenshot.png is provided

Question 5:

2018-10-01 23:29:09,117 - INFO # Hello World!
2018-10-01 23:29:09,125 - INFO # You are running RIOT on a(n) openmote-b board.
2018-10-01 23:29:09,132 - INFO # This board features a(n) cc2538 MCU.







