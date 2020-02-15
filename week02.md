# Common Code Vulnerabilities
Date: 20200209

Common Vulnerabilities Types
* [CVE: Common Vulnerabilities and Exposures](http://cve.mitre.org/)
* [Exploit Database](https://www.exploit-db.com/)
* [NVD: National Vulnerabilty Datbase](https://nvd.nist.gov/)

Terminology:
* Threat: potential cause of incident
* Vulnerability: weakness of asset and group that can be exploited by one or more threats
* Exploit: series of steps to take advantage of vulnerability
* Attack: assault on system security from an intelligent threat

TODO: See [OWASP Top 10 Vulnerabilities for web app](https://owasp.org/www-project-top-ten/)

TODO: See [SANS Top 25 Software Errors](https://www.sans.org/top25-software-errors/)

These are common software vulnerabilities (TODO: elaborate, this is the main foccus of this week material):
* Buffer overflow
* Unvalidated input
* XSS
* Race conditions
* Dangling pointer vulnerability
* Broken auth and session mgmt
* Insecure direct object references
* Access control problems

## Buffer overflow
Since c doesn't check buffer boundary, we can overflow the buffer and overwrite another memory area that should be occupied by other data and program. By exploiting this, once can be able to alter control flow of a program.

To understand more about this, one need to learn about memory management. Generally, memory section can be divided as follow:
* Kernel space
* Stack
* Memory Mapping segment
* Heap
* BSS Segment
* Data Segment
* Text Segment

Stack consists of stack frame. Following is stack frame layout (from high address to low address):
* local vars
* return address
* Previous frame pointer

How to alter control flow or to inject malicious code using buffer overflow? First we need to inject malicious code, usually through user input. Overflow the buffer to overwrite the return address of the stack. Make the new return address points to the malicious code.

Heartbleed is one of recently famous buffer overflow vulnerabilities.

TODO: Read [heartbleed paper](https://jhalderm.com/pub/papers/heartbleed-imc14.pdf) as example of bufferoverflow vulnerabilities.

## Unvalidated input
### SQL Injection
This vulnerabilties happen when there is mixing between command and parameters. Since the input is not validated correctly, input which means to be parameters are treated as part of command. One example:

```
select * from user where username=<username> and password = <password>
```

If we pass `password` parameter as `foo or 1 = 1`, then regardless what is actual password even though it is mismatched with the passed password, it will always give the correct result.

### XML injection
Similar with SQL injection but now it is exploited in xml input. TODO: might be applicable in json too?

## Race Condition
TBD

## Dangling Pointer
When memory is freed, we also need to make sure to set the pointer to point to null so that it wouldn't be accidentally point to another data if somehow the memory is occupied by something else.

## Others memory safety
### Access errors
* Buffer overflow
* Buffer over-read
* Race condition
* Invalid page fault
* Use after free
### Uninitialized vars
* Null pointer
* Wild pointer
### Memory leak
* Stack Exhaustion
* Heap exhaution
* Double free
* Invalid free
* Mismatched free: TODO what is this
* Unwanted aliasing: TODO what is this
