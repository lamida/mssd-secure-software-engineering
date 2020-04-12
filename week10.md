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
* Determining whether a program satisfies a property by the means of exhaustive searching.
* Pioneers: Edmund D. Clarke, Allen Emerson, Joseph Sifakis. Turing award 2007
* Intel i7 processor (8 cores, millions of registers) is verified by symbolic model checking without a single test case
* The slam project (static driver verifier, shipped with Windows 7) from Microsoft successfully detected many bugs in many driver software

# Model, property, model checker
* Model: representation of the system: Kripke Structure
* Property: specification that the final system is expected to satisfy
* Model checker: tool that accept a model and a property as inputs and outputs. Yes if the given model satisfies given speficifications and generates a counterexample otherwise

# Kripke Structure
We model program using kripke structure

A Kripke structure is a tuple (S, R, L, I)
* S: set of states
* R: set of relations between states
* I: non-empty states of initial states
* L: lables each state by a set of valid atomic propositions in the state

# Property
* Temporal logic: succint and precise way of describing program properties
* Amir Pnueli

# Linear Temporal Logic
* There is only one linear future. Program = set of sequences of states
* LTL is built up from a finite set of propositions, the logical operator "not" and "or", and the following temporal model operators
    * X: next
    * G: always
    * F: eventually
    * U: until
    
Semantics: given a sequence of states of a Kripke Structure:
* *p* is satisfied at the i-th state of the sequence if p is one of the propositions labeling the state
* *X* p is satisfied at the i-th state of the sequence if p is satisfied at the (i+1)-th state
* *G* p is satisfied at the i-th state of the sequence if p is satisfied at every state from (inclusive) the i-th state
* *F* p is satisfied at the i-th state of the sequence if p is satisfied at least one state from (inclusive) the i-th state
* p *U* q is satisfied at the i-th state of the sequence if there exists a future (i+k+1)-th state satisfying q and p is satisfied at every state from (inclusive) the i-th state until the (i+k+1)-th state (exclusive)
    



