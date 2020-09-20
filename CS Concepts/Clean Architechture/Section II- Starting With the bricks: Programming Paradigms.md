Alan turing conceived programmable machines. By 1945, Turing was writing real programs on real computers in code that we would recognize. His language was binary. He used loops, branches, assignment, subroutines, stacks and other familiar structure. Then came assemblers removing need for binary conversion. In 1951, Grace Hopper invented A0, first compiler. Fortran came in 1953. Then came flood of languages.
Paradigms are ways of programming. This is unrelated to language itself. There are three paradigms.

# Chapter 3:- Paradigm Overview
Three paradigms are:-
- Structured Programming - imposes discipline on direct transfer of control
- Object - Oriented Programming - imposes discipline on indirect transfer of control
- Functional Programming - imposes discipline on assignment<br>
Each paradigm removes capabilities from the programmer. Paradigm tell us what not to do, more than they tell us what to do. These paradigms align with the three big concerns of architecture: functions, separation of components, and data management.

# Chapter 4:- Structured Programming
Started by Dijkstra. He started in the era of vacuum tubes, when computers were huge, fragile, slow, unreliable and limited. Language was binary or assembly. Input was in punch card. Edit/compile/test loop was hours to days. He recognized program of any complexity contains too many details for a human brain to manage without help. Overlooking one small detail results in programs that may seem to work, but fail in surprising ways.
## Proof
Dijkstra solution was applying mathematical discipline of proof. Programmers would use proven structures and tie them together with code that they would then prove correct themselves. Dijkstra found goto prevented decomposition into smaller units. Only good usage of goto was if/then/else and do/while. Jacopini proved all programs can be constructed from just three structures:- sequence, selection(if/else) and iteration(do/while). Dijkstra used enumeration as mathematical proofs. such proofs were laborious and complex. In 1968, he proclaimed goto is harmful. Today none of language give us option to use undisciplined direct transfer of control.
## Functional decomposition
Structural programming ==> recursive decomposition into provable units. **But the proofs never came.** Formal proofs are not considered today as appropriate way to produce high quality software.
## Science to rescue
Science work by proving statements are true, but rather by proving statements false. Those statements that we cannot prove false, after much effort, we deem to be true enough for our purpose. Software is like science. We show correctness by failing to prove incorrectness, despite our best efforts. Structured programming forces us to recursively decompose a program into a set of small provable functions. We can then use tests to try to prove those small provable functions incorrect. If such tests fail to prove incorrectness then we deem the functions to be correct.

# Chapter 5:- Object-Oriented programming
Nygaard moved the function call stack frame to the heap and invented OO.  Common definitions of OO - "OO is combination of data and functions.", "A model of real world", "OO is code supporting Encapsulation, inheritance and polymorphism"
## Encapsulation
- Private members and public members of a class.
- C had perfect encapsulation by header file
- C++ wants member variables of class in header file and Java has removed separate declaration and definition
- Thus encapsulation has only weakened with OO languages
## Inheritance
- Inheritance is simply redeclaration of a group of variables and functions within enclosing scope. This is how C++ implements inheritence.
- In C you would make a struct namedPoint and then cast its arguments to Point struct.
- OO made masquerading of data structure significantly more convenient
## Polymorphism
Consider getchar() function of C. Unix Os required every IO device to provide standard functions:- open, close, read, write and seek and FILE data structure contains pointers to these functions. The IO driver will define those functions and load up a FILE data structure with addresses. So, when a getchar() is called it simply calls function pointed to by the read pointer of the FILE data structure pointed to by STDIN.  In C++ every virtual function within class has a pointer in a table called a vtable and calls to virtual functions go through that table. Constructors and derivatives simply load their version of those functions into vtable of the object being created.
_Polymorphism is application of pointers to functions._
The problem with explicitly using pointers to functions are dangerous. These are driven by manual conventions of initialization, calling etc. Any resulting bug is hard to track down and eliminate. OO removes these conventions and therefore these dangers. OO makes polymorphism trivial.
_OO imposes discipline on indirect transfer of control._
## Power of Polymorphism
Consider copy programs associated with IO devices. All IO devices have become plugins to the copy program. We learnt in 1950s that our programs should be device independent. Most programmers did not extend the idea to their own programs because using pointers to functions was dangerous. OO allows the plugin architecture to be used anywhere for anything.
## Dependency inversion
Without Polymorphism, source code dependencies followed the flow of control. High level functions needed to mention module that continued the callee. With interface we achieve dependency inversion. In OO any source code dependency can be inverted. A software architect can rearrange the source code dependencies of your system so that database and the UI depend on business rules rather other way round. Source code of business rules never mention UI or the database. When source code in a component change only that component needs to be redeployed. This is **independent deployability.** This also leads to **independent developability.**
_OO is ability through the use of polymorphism to gain absolute control over every source code dependency in the system._

# Chapter 6:- Functional Programming   
Variables in functional languages do not vary. All race conditions, deadlock conditions and concurrent update problems are due to mutable variables. No race condition can occur if no variable is updated. You can't have deadlocks without mutable locks.
## Segregation of  Mutability
Segregate the application into mutable and immutable components. The immutable components perform their tasks in purely functional way without using any mutable variables. Transactional memory is required for mutable variables. It protects those variables with a transaction or retry-based scheme.Well structured applications will be segregated into those components that do not mutate variables than that do. Architects then push as much processing into the immutable components and drive as much code as possible out of those components that must allow mutation.
## Even sourcing
Consider we need a banking application where we need balances of customer when deposit and withdrawal takes place(mutable component). If only transactions are stored no mutable variables will be required.
_Event sourcing is a strategy wherein we store the transaction but not the state. When state is required, simply apply all the transactions_
Shortcuts are possible. Save the state at particular frequency(midnight for bank balance). We need to execute transactions since midnight. Nothing ever get deleted or updated. Thus there is no concurrent update issue. This is way source code control system works.
## Conclusion
Structured --> discipline on direct transfer, OO--> discipline on indirect transfer, Functional --> discipline on variable assignment<br>
Software, the stuff on computer programs is composed of sequence, selection, iteration and indirection(??).

# Appendix
## Memory management primer
![](media/Memory%20management.png)
## Virtual function
In object-oriented programming, in languages such as C++, and Object Pascal, a virtual function or virtual method is an inheritable and overridable function or method for which dynamic dispatch is facilitated. This concept is an important part of the (runtime) polymorphism portion of object-oriented programming (OOP). In short, a virtual function defines a target function to be executed, but the target might not be known at compile time.
