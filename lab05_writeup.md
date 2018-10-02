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

Question 3: -------TODO---------

In main.c of the hello-world example, the RIOT_BOARD and RIOT_MCU are used but not explicitly defined in the file. In C, we define macros using `#define`. Make can do the same by prepending the `-D` flag. Use your text editor (e.g. ctrl+shift+f in Sublime Text) to search the entire codebase under the RIOT base directory for the specific file named `Makefile.include` that defines RIOT_BOARD and RIOT_MCU. What is the relative path to the file?

RIOT-EE250/Makefile.include

Question 4:

question_4_screenshot.png is provided

Question 5:

2018-10-01 23:29:09,117 - INFO # Hello World!
2018-10-01 23:29:09,125 - INFO # You are running RIOT on a(n) openmote-b board.
2018-10-01 23:29:09,132 - INFO # This board features a(n) cc2538 MCU.


Question 6: --------TODO--------

Which directory should you go into to find code related to a specific target platform? What directory contains the implementation of the network stack? Answer this in your lab writeup.


Question 7: -------TODO---------

What are the three essential variables that need to be defined in the Makefile? Answer this in your lab writeup.

Question 8:-------TODO---------

How do you include a new module, let’s say ‘sixlowpan’, into your code? Answer this in your lab writeup.

Question 9:

channel 20

2018-10-02 00:23:04,444 - INFO #  ifconfig 4 set channel 20
2018-10-02 00:23:04,451 - INFO # success: set channel on interface 4 to 20
txtsnd 4 6f:f3 is_anyone_here?
2018-10-02 00:23:05,599 - INFO #  txtsnd 4 6f:f3 is_anyone_here?
> 2018-10-02 00:23:05,647 - INFO #  PKTDUMP: data received:
2018-10-02 00:23:05,656 - INFO # ~~ SNIP  0 - size:  29 byte, type: NETTYPE_UNDEF (0)
2018-10-02 00:23:05,672 - INFO # 00000000  59  45  53  3A  2D  35  30  2E  36  30  36  30  33  31  31  4E  YES:-50.6060311N
2018-10-02 00:23:05,687 - INFO # 00000010  2C  31  36  35  2E  39  36  33  39  39  37  36  57              ,165.9639976W
2018-10-02 00:23:05,696 - INFO # ~~ SNIP  1 - size:  12 byte, type: NETTYPE_NETIF (-1)
2018-10-02 00:23:05,702 - INFO # if_pid: 4  rssi: 42  lqi: 242
2018-10-02 00:23:05,705 - INFO # flags: 0x0
2018-10-02 00:23:05,709 - INFO # src_l2addr: 6f:f3
2018-10-02 00:23:05,714 - INFO # dst_l2addr: ed:dc
2018-10-02 00:23:05,722 - INFO # ~~ PKT    -  2 snips, total size:  41 byte

Coordinates:

-50.6060311N, 165.9639976W






