Alan turing conceived programmable machines. By 1945, Turing was writing real programs on real computers in code that we would recognize. His language was binary. He used loops, branches, assignment, subroutines, stacks and other familiar structure. Then came assemblers removing need for binary conversion. In 1951, Grace Hopper invented A0, first compiler. Fortran came in 1953. Then came flood of languages.
Paradigms are ways of programming. This is unrelated to language itself. There are three paradigms.

# Chapter 3:- Paradigm Overview
Three paradigms are:-
* Structured Programming - imposes discipline on direct transfer of control
* Object - Oriented Programming - imposes discipline on indirect transfer of control
* Functional Programming - imposes discipline on assignment
Each paradigm removes capabilities from the programmer. Paradigm tell us what not to do, more than they tell us what to do. These pradigms align with the three big concerns of architecture: functions, separation of components, and data management.

# Chapter 4:- Structured Programming
Started by Dijkstra. He started in the era of vacuum tubes, when computers were huge, fragile, slow, unreliable and limited. Language was binary or assembly. Input was in punch card. Edit/compile/test loop was hours to days. He recognized program of any complexity contains too many details for a human brain to manage without help. Overlooking one small detail results in programs that may seem to work, but fail in surprising ways.
## Proof
Dijkstra solution was applying mathematical discipline of proof. Programmers would use proven structures and tie them together with code that they would then prove correct themselves. Dijkstra found goto prevented decomposition into smaller units. Only good usage of goto was if/then/else and do/while. Jacopini proved all programs can be constructed from just three structures:- sequence, selection(if/else) and iteration(do/while). Dijkstra used enumeration as mathematical proofs. such proofs were laborious and complex. In 1968, he proclaimed goto is harmful. Today none of language give us option to use undisciplined direct transfer of control.
## Functional decomposition
Structural programming ==> recursive decomposition into provable units. **But the proofs never came.** Formal proofs are not considered today as appropriate way to produce high quality software.
## Science to rescue
Science work by proving statements are true, but rather by proving statements false. Those statements that we cannot prove false, after much effort, we deem to be true enough for our purpose. Software is like science. We show correctness by failing to prove incorrectness, despite our best efforts. Structured programming forces us to recursively decompose a program into a set of small provable functions. We can then use tests to try to prove those small provable functions incorrect. If such tests fail to prove incorrectness then we deem the functions to be correct.

#Chapter 5:- Object-Oriented programming
Nygaard moved the function call stack frame to the heap and invented OO.  Common perceptions - "OO is combination of data and functions.", 
