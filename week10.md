# Formal Verification: Software Model Checking
Date: 20200406

# Testing vs Formal verification
Testing
* aims to reveal bugs
* easy to apply
* never complete
* every system must be tested

Formal Verification
* aims to show the absence of bugs based on logic
* could be sound and complete
* is not easy to apply
* formal verification is for system that can't afford any errors: e.g. control software for nuclear plants, space missions, high speed trains, autonomous cars
* some system are more secure if they are verified
* alls ystems are better off if they could be verified

Djikstra: Testing shows the presence, not the absence of bugs.

# Formal Verification is hard
Almost all interesting verification problems are undecidable, including those related to secure coding (e.g. no buffer overflow, no race condition)
Example: the halting problem

# Formal verification techniques
* software model checking
* theorem proving
* symbolic execution

# Software Model Checking
Determining whether a program satisfies a property by the means of exhaustive searching.
Pioneers: Edmund D. Clarke, Allen Emerson, Joseph Sifakis. Turing award 2007
Intel i7 processor (8 cores, millions of registers) is verified by symbolic model checking without a single test case
The slam project (static driver verifier, shipped with Windows 7) from Microsoft successfully detected many bugs in many driver software






