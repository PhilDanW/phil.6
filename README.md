# Project 6
# Memory Management

## Author: Philip Wright

Operating System Simulator: Virtual Memory Management
Second-Chance FIFO Page Replacement Algorithm
OSS fork/execs "user" processes at bounded intervals on a simulated sys clock.
Up to 18 concurrent "user" processes continually request memory from OSS.


Usage: ./oss [-p <1-18> ] p: number of concurrent users allowed


User processes request a memory address that they know only as 0-31. OSS 
dictates a page table and keeps track of where each user's page exists in 
memory. If memory fills (256 frames available), the virtual memory process 
begins. This only happens with > 8 users. If a page fault occurs, OSS 
adds that user to a suspended queue and does not free it to continue looping 
until 15ms have passed to simulate reading from disk. When users terminate, 
each dirty bit in memory adds to the sim clock to simulate writing that 
dirty page from the frame in memory back to disk.
