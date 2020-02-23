# Defensive Coding 2 Java
Date: 20200224

## Java Security
### JVM
* verifies bytecode and enforces runtime constraints such as array bounds checking;
* disallows programs to perform certain potentially unsafe operations such as pointer arithmetic or unchecked type casts;
* disallows manual control over memory allocation and deallocation;
* supports automatic garbage collection.
### Security API
* cryptographic algorithms
* authentication, and secure communication protocols
* thread-control and concurrent data-structures
### Security Manager
* allows users to run untrusted bytecode in a "sandboxed" environment

## SEI CERT Java Coding Standard
156 rules
https://www.cert.org/secure-coding/

* Input valuation and data sanitization
* Object-orientation
* Locking and thread-safety
* Visibility and atomicity
 
## Input Validation and Data Sanitization
* DS00-J. Sanitize untrusted data passed across a trust boundary
* IDS01-J. Normalize strings before validating them
* IDS11-J. Eliminate non-character code points before validation

## Object Orientation
* OBJ00-J. Limit extensibility of classes and methods with invariants to trusted subclasses only
* OBJ01-J. Declare data members as private and provide accessible wrapper methods
* OBJ02-J. Preserve dependencies in subclasses when changing superclasses
* OBJ04-J. Provide mutable classes with copy functionality to safely allow passing instances to untrusted code
* OBJ05-J. Defensively copy private mutable class members before returning their references
* OBJ10-J. Do not use public static non-final variables
 
## Locking and Thread-Safety
* LCK00-J. Use private final lock objects to synchronize classes that may interact with untrusted code.
* LCK06-J. Do not use an instance lock to protect shared static data

##  Visibility and Atomicity
* VNA00-J. Ensure visibility when accessing shared primitive variables
* VNA02-J. Ensure that compound operations on shared variables are atomic
* VNA03-J. Do not assume that a group of calls to independently atomic methods is atomic.
 
 
