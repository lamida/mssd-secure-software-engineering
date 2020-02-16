# Defensive Coding 1 C/C++
Date: 20200217

Secure Coding Utopia vs Reality

SEI CERT Coding Standard
C Coding Standard: 99 rules
C++ Coding Standard: 83 rules
https://www.cert.org/secure-coding/

Overflow
* INT32-C: Ensure that operations on signed integers do not result in overflow. 
* ARR30-C. Do not form or use out-of-bounds pointers or array subscripts
* STR31-C. Guarantee that storage for strings has sufficient space for character data and the null terminator
 
INT32-C Risk Level is high because the overflown value can be used as the number to allocate for a buffer and can lead to arbitrary code execution.

Memory Safety
* EXP33-C: Do not read uninitialized memory
* DCL30-C: Declare objects with appropriate storage durations
* MEM30-C: Do not access freed memory
* MEM51-CPP: Properly deallocate dynamically allocated resources
* ERR51-CPP: Handle all exceptions
* STR53-CPP: Range check element access
* ERR57-CPP: Do not leak resources when handling exceptions
