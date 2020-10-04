# Chapter 15 - What is Archtecture
___
Software Architects
- Best of programmers
- guide the rest of team toward a design that maximizes productivity
- They write code to experience problems faced by rest of programmers

> Goal of Architecture - Lease as many options open as possible for as long as possible

Architecture has very little bearing on whether system works. Its role is passive and cosmetic. It supports life cycle of system. 
- Easy to understand
- Easy to maintain
- Easy to deploy

It minimizes lifetime cost of the system and maximizes programmer productivity.

Development - 
Team structure can have an implication on Architecture. Small team and work together to develop a monolithic system without well-defined components. Architecture might create impediment of a superstructure.
If there are five different teams then system is divided into well-defined components with reliably stable interfaces. There might be five components which will drive the development schedule.

Deployment - A software should be easily deployable with single action. Lets say in early development a system is decided as micro service. Its easy to develop. 
At deoployment, number of micro-services has become daunting that configuring connections between them and timing of their initiation are a source of error. A hybrid of services and in-process components and a more integrated means of managing interconnection would have been better.

Operations - Less dramatic impact. Any operational difficulty can be resolved by throwing more hardware. Hardware is cheap and people are expensive means that architectures taht impede operation are not as costly as architectures that impede development, deployment and maintainance. 
Most important role of architecure in software is it communicates the operational needs of the system. It makes the oepration of the system readily apparent tot hte developers which simplified their understanding adiding in development and maintainance.

Maintainance - Most costly. Primary cost of maintainance is spelunking and risk. **Spelunking** is cost of digging through existing software trying to determine best place and strategy to add new feature and repair a defect. there is always likelihood of creating inadvertent defect adding to cost of risk. These costs are mitigated by isolation of components through stable interfaces. 

## Keeping options open
___
All software systems have two components. 
1. Policy - business rules and procedures
1. Detail - Enables communication of stakeholders with policy without affecting its behavior. It includes IO devices, database, web systems, servers, frameworks, communication protocols etc.

Architecture delays and defers details. Examples
- If architect is careful high level policy will not care if the database is relational, distributed, hierarchichal or just plain file
- You don't need to decide if the system will be delivered over the web. You should not choose web server early in developement
- High level policy should not case about micro service/SOA or interface of REST
- High level policy should not care how dependencies are resolved

High level policy is developed without committing to the details that surround it. The decision is taken when there is more information to make a proper decision.
Longer options are open leaves more room for experimentation. 

> A good architect maximizes the number of decisions not made

## Examples
1. Device independence - In 1960s all the code was written to manipulate card readers and card punches. When magnetic tape came everyone had to take a big job of rewriting to use magnetic tape. 
This led to invention of device independence and OCP was born. This helped writer at a letter date to immediately change system to an IBM 360 to send large amount of junk mail. 
2. Writer worked in an org where data was stored in cylinders with their locations mapped directly. There was hard writing of address everywhere. A new disk drive with more heads would require rewrite of complete software. Relative address solved the problem. Disk was now a linear array of sectors and there was a conversion routine from this sector to cylinder, head and sector. 

# Chapter 16 - Independence
___











# Appendix
___
Difference between micro service architecture and SOA
![](media/Architecture%20Types.png)
