# Operating Systems Laboratory Course Projects

This repository contains my Operating Systems Laboratory course projects at University of Tehran.

A modified [xv6](https://github.com/mit-pdos/xv6-public) operating system with several extra features such as various new system calls, multilevel queue scheduling, and synchronization.

1. Lab1 : Introduction to the xv6 operating system kernel
2. Lab2 : System Calls and Processes
3. Lab3 : Process Scheduling
4. Lab4 : Synchronization
5. Lab5 : Memory Management (Implementing mmap in xv6) 

## Part 1. Introduction to xv6

* Added contributors names to boot message.
* Shell features:

    1. ```CTRL + T``: Move the last two letters before the cursor
    2. ```CTRL + O``: Uppercase all letters after the cursor
    3. ```CTRL + A``: Move the cursor to the beginning of the line

* Calculate all divisors of a number by ```factor``` command and store the result in factor_result.txt.

## Part 2. System calls
* ```calculate_sum_of_digits(int n)```: زalculate the sum of input number digits
* ```void get_file_sectors(int fd, <parameter storing returned sector addresses>)```: find the address of file sectors
* ```int get_parent_pid()```: get parent's process
* ```set_process_parent(int pid);```: Change the parent of a process

## Part 3. CPU Scheduling
Modified the scheduler by adding 4 different levels for processes. 

1. Level 1: Round Robin (RR)
2. Level 2: Last Come First Serve (LCFS)
3. Level 3: Modified Highest Response Ratio Next (MHRRN)

Some system calls added: 
* ```set_level(int pid, int level)```: sets the level for the process
* ```set_mhrrn_param_process(int pid, int priority)```: sets the MHRRN parameter at the process level
* ```set_mhrrn_param_system(int priority) ```: sets the MHRRN parameter at the system level
* ```print_process(void)```: show processes and their information such as state and scheduler queue

## Part 4. Synchronization
Simulation of the problem of Dining Philosophers with 5 Philosopher.

Some system calls added: 
* ```sem_init(i, v)```: the semaphore in the i-th house creates an array with a number v for maximum processing within the critical area.
* ```sem_acquire(i)```: when a process wants to enter the critical area, it calls a system call.
* ```sem_release(i) ```: when a process wants to exit the critical area, it calls a system call.

## Part 5. Memory Management 
Implementing mmap in xv6

Some system calls added: 
* ```int get_free_pages_count()```: calculate and return the number of available free pages from physical memory
* ```void *mmap(void *addr, size_t length, int prot, int flags, int fd, int offset)```: mmap system call

## How to use ? 
you can make this kernel using `make` command.
also you can run this kernel on qemu virtual machine using `make qemu` command.

Contributor : [Emad Emami](https://github.com/emad008)
