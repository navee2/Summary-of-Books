The SOLID principles tell us how to arrange our functions and data structures into classes, and how those classes should be interconnected. Goal is to create mid-level(module level) software structures that:
- Tolerate change
- easy to understand
- basis of components that can be used in many software systems

# Chapter 7:- SRP: The Single Responsibility Principle
_A module should have one and only one reason to change._
It should not be a module should do just one thing(which is basically function). From a stakeholder perspective it translates to<br>
_A module should be responsible to one and only one actor(people who require change)._<br>
What is a module? - Simply a file(for java kind of langulage). Cohesive set of functions and data structures. Following are symptoms of violating it.
## Symptom 1: Accidental Duplication
Consider class Employee with 3 methods:-
- calculatePay() - used by accounting department
- reportHours() - used by HR
- save() - used by database admins
Now suppose calculatePay ----> regularHours <-----reportHours
Now finance team wants change in non-overtime hours calculations which HR doesn't want. Developer changes reportHours and is validated by Finance team. Now this will cause HR millions of dollars before figuring what happened. SRP says to separate the code that different actors depend on.

## Symptom 2: Merges
Suppose database team wants a change in schema of employee and HR wants to change format of hours report. Two different deveopers from different team check out Employee class. Unfortunately their changes collide. Merge puts both DB and HR team at risk along with others dependent teams.

## Solutions
Separate the data from the functions. Three classes are not allowed to know each other. Problem being developers now have three classes that they have to instantiate and track.  A solution is to use Facede pattern
![](media/SRP.png)
EmployeeFacade has little code and is responsible for instantiating and delegating to classes with the functions.<br>
Some developers prefer the most important business rules closer to the data.  In that case most important methods will be in original Employee class and then using that class as a Facade for the lesser functions.
![](media/SRP2.png)

## Conclusion
SRP is about functions and classes. At component level it becomes Common closure Principle. At architectural level it becomes axis of change responsible for the creation of Architectural boundaries.
