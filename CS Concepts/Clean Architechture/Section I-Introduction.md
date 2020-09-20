# Introduction
Getting something to work "once" just isn't that hard. Getting software right is hard. It takes passion for the craft and the desire to be a professional. When software is done right, it requires fraction of the human resources to create and maintain. Changes are simple and rapid. Effort is minimized, and functionality and flexibility are maximized.
Programming hell - interconnected systems that every change takes weeks and involves huge risk.

# Chapter 1:- What is Design and Architechture
They are basically same. Architechture is used in context of something high level divorced from lower level details. Design usually imply structure and decisions at a lower level.  Low level details and high level decisions are both part of whole design. There is simply a continuum of decisions from the highest level to lowest levels

## Goal of software Architechture
Minimize the human resources required to build and maintain the required systems. If effort required to meet the needs of customer grows with each new release, the design is bad.

## Case study
Real data from a company
* Growth of engineering staff - 15 - 1200 in 8 years
* Productivity - 3000 lines of code to 7000 lines of code with no change in last 4 years
* Cost per line of code - $10 - $400  in 8 years
These trends are unsustainable

## Signature of mess
Productivity bottoms asymptotically approaching zero. This is despite everyone working hard. All efforts are diverted away from features and is consumed with managing the mess. Developers job is moving mess from one place to next and next.  
**Executive View -** One hopes that revenue will outpace costs justifying the expense. Initial few thousand dollars per month bought lots of functionality, final $20 million bought almost nothing. **Action -** stamp their feet and rage at developers.

Clean well designed code matters. We can clean it up later is a **lie**. You have got a horde of competitors on your tail, and you have to stay ahead of them by running as fast as you can. So, developers never switch mode. Mess builds and productivity continues its asymptotic approach towards zero. Biggest lie is writing messy code makes them go fast in short term and just slows them down in long term. Fact is making messes is always slower than staying clean. Reference to Experiment by Jason Gorman. TDD code writing was 10% faster in different experiment than without TDD in worst case.
_The only way to go fast, is to go well._

Developers may think that the answer is to start over from scratch and redesign the whole system. The reality is less rosy. The overconfidence will drive the redesign into the same mess as the original project.

## Conclusion
Build a system with a design and an architecture that minimize effort and maximizes productivity. One needs to know which attributes of system architecture lead to that end.

# Chapter 2:- A Tale of Two values
Software value to stakeholders - Behavior and Architecture
## Behavior - implement requirement + fix bugs
Write code to satisfy stakeholder's machines to satisfy those requirements. If requirements are violated, developers need to debug and fix the problem.
## Architecture
"Soft"ware -- easily changeable - When stakeholders change their mind about a feature that change should be simple and easy to make. The difficulty in making such a change should be proportional only to the scope of the change and not to the shape of the change.
From stakeholder's point of view they are simply providing a stream of changes of roughly similar scope. From developer's point of view, the stakeholders are giving them a stream of jigsaw puzzle pieces that they must fit into puzzle of ever-increasing complexity. Each new request is harder to fit that last, because the shape of system does not match the shape of request.
## The greater value
* A program that works perfectly but is impossible to change won't work when requirements change
* Program that doesn't work but is easy to change then one can make it work and keep working as requirements change
There are systems that are practically impossible to change because cost exceeds the benefit of change. Many systems reach that point in some of their features or configurations. While people say current functionality is important than later flexibility its wrong.

## Analogy of Eisenhower's matrix
Behavior is urgent while architecture is important. In order of priorities
1. urgent and important
2. not urgent and important
3. Urgent and not important
4. Not urgent and not important<br>
The mistake is managers and developers often make is to elevate items in position 3 to position 1. Dilemma of software developers is business managers are not well equipped to evaluate the importance of architecture. Responsibility of software development team to assert the importance of architecture over the urgency of features.

## Fight for architecture
A responsible software team fights for architecture. Its fight among development team, marketing team, management, operations for the best results for company.  Effective software development teams tackle the struggle head on. They consider themselves as equal stakeholder. It's a big part why you are hired. Features and functions need to be easily developed, easily modified and extended.
