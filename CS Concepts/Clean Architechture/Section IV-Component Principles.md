Solid principles tell us how to arrange bricks into walls and rooms. Component principles tell us how to arrange rooms into buildings.

# Chapter 12:- Components
Components are units of deployment. They are jar files, dll files etc. They are linked together to form a single executable. Well designed components are independently deployable and independently developable.
## History of components
- Include source code of library functions with applicaiton code into a single programming(libraries in source and not in binary)
    - compilation took long time
- Function library loaded at a known address. This led to fragmentation of programs
- Relocability - compiler was changed to output binary code that could be relocated in memory with smart loader.  Allowed programmers to load functions they needed
    - compiler emitted names of external references if used. If a program defined a library function, the compiler would emit that name as an external definition. The loader would link the external references to the external definitions once it had determined where it had loaded those definitions.
- Linkers - Allowed programmers to divide their programs onto separately compilable and loadable segments
    - Function libraries were stored on devices(very slow)
    - As programs grew larger, more library functions accumulated in libraries, a linked loader took more than hour to just load the programs
- C - source modules were compiled into .o files and fed to linker that could be quickly loaded - compiling all modules took time
- By mid-90s computers became fast, link time decreased to seconds and linking loaders again became feasible
- Today .jar, dlls are routinely shipped as plugins to existing applications
- The dynamically linked files which can be plugged together at runtime are the software components of our architecture.

# Chapter-13: Component Cohesion
## The reuse/release equivalence principal(REP)
> the granule of reuse is the granule of release

- We are living in age of software reuse. Tools such as Maven, Leiningen and RVM help in module management.
- REP implies to reuse software components, components need to be tracked through a release process and are given release numbers
    - enables compatibility, timeline for new release and change release correspondence.
    - The classes and modules that are fored into a component must belong to a cohesive group
    - The classes and modules that are grouped together into a components should be releasable together.

## The common closure principal(CCP)
> Classes that change for same reasons and at same item should be gathered into components. --- similar to SRP

Maintainability is more important than reusability. If code must change, it should be within a components. Relation to OCP - Closed to same types of changes are in same compoenents. When a change in requirements comes along, change should be restricted to a minimal number of components.

## The common reuse principle(CRP)
> Don't force users of a component to depend on things they don't needs

A component has classes which have lots of dependencies on each other. For example, container classes and their iterators. When we depend on a component, we want to make sure we depend on every class in that component. CRP is similar to ISP.

> Don't depend on things you don't need.

## The tension diagram for component Cohesion(reuability vs developability)
- REP and CCP are inclusive principle(make components larger). CRP is exclusive principle(makes component smaller)
    - Missing REP ---> Hard to reuse
    - Missing CCP - too many components change
    - Missing CRP - Too many unneeded releases.
- Importance changes during software development. Initially CCP is much more important than REP because develop-ability is more important than reuse.
Component structure of a project can vary with time and maturity(It shifts from less reusability to more reusability).

# Chapter 14 - Component Coupling(Develop-ability vs logical design)
## The acyclic dependence principle
> Allow no cycles in the component dependency graph

- The morning after sydrome - someone changed something you depend on
    - Problem in large projects
    - Everyone keeps on changing their code to make it work with last change someone else made
- Two proposed solutions
1. The weekly build - Used in medium sized projects. All developers work independent 4 days a week and integrate and build system on Friday. As project grows integration burden increases. Integration and testing become increasingly harder to do, and the team loses the benefit of rapid feedback.
1. Eliminating dependecy cycles - Partition development environment into releasable components. Component is responsibility of a developer or team of developers. Components are released with a relase number for others to use. Teams decide whether to use new component. Integration happens in small increments. At no point all developers must come together and integrate everyting they are doing.There can't be cycle dependency now. When its time to release whole system, process proceeds from bottom up. lowest level component is first compiled tested and released. This then moves upwards.

### Effect of cycle in the component dependency graph
Creates one large component. All developers must exactly use same release of one another's component. There is proper order to build components.
Breaking the cycle
1. Apply DIP - Create an interface within another component.
2. Create a new component that both depend upon. This implies component structure is volatile in the presence of changing requirements. The dependency structure will grow.

### Top-Down design
Component structure can't be designed top down. It is not first ting aobut the system designed. It evolves as the system grows and changes. component dependency diagrams have little to do with describing function of application. They map buildability and mainatainability.
In dependency structure we don't want components that change frequently to affect stable components. We don't want GUI cosmetic chagnes to affect business rules. If we try to design components before classes, we would be unaware of reusable components and would create dependency cycles.

## The stable depencencies principle
> Depend in the dicrection of stability

Volatility is necessary if design has to be maintained. We ensure that modules that are intended to be easy to change aer not depended on by modules that are harder to change.
### stability
> Requires large work to change

A component with losts of incoming dependencies is very stable because it requires a great deal of work to reconcile any changes with all the dependent components.  If components A, B and C use component X then X is stable. X is responsible for three components. It is independent.
If no other component depend on a component but it depends on large number of component then its dependent and unstable.  

### Stability metrics
- Fan in - # incoming dependencies(in terms of #classes)
- Fan out = # outgoing dependencies
- Instability = Fan-out/(Fan-in + fan out)

In Java instability can be calculated by counting import statements and qualified names. Instability decreases in direction of dependency.
If all components are stable, system would be unchangeable. If a stable component depends on flexible component use DIP.

### Abstract Components
Contains only abstract classes.In static languages these aer ideal targets for less stable components to depend on. In dynamically typed language, dependecy inversion does not require either declaration or inheritance of interface.

## Stable abstraction principle
> A component should be as abstract as it is Stable
 
