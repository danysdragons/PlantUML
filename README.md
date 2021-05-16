## **PlantUML - Guide to Basic Usage** ##

Note: I am **not** the creator of PlantUML, and this repository does not host the source code for PlantUML. This repository is just intended *to illustrate basic usage of PlantUML*.

PlantUML provides a declarative syntax for generating various UML diagrams: class diagrams, sequence diagrams, use case diagrams etc.

An example of the markup for a state transition diagram


```
@startuml
scale 800 width

[*] -> State1 : entry1
[*] -> State1 : entry2
State1 --> State2 : Succeeded
State1 --> [*] : Aborted
State2 --> State3 : Succeeded
State2 --> [*] : Aborted
state State3 {
  state "Do Something Else" as doSomething
  state "Accumulate Enough Data\nLong State Name" as long1
  long1 : Just a test
  [*] --> long1
  long1 --> long1 : New Data
  long1 --> ProcessData : Enough Data
  state "Process More Data" as ProcessData2
  ProcessData --> ProcessData2 :  Woot
  doSomething --> long1 : Wootful!
  ProcessData2 --> [*]
}
State3 --> State3 : Failed
State3 --> [*] : Succeeded / Save Result
State3 --> [*] : Aborted

@enduml
```
**What it looks like after rendered to .png file:**

![alt text](https://raw.githubusercontent.com/danysdragons/PlantUML/master/State%20Diagram/stateDiagram.png "A nice state machine diagram, woot!")

The renderer is distributed as a single Java *jar* file, ***plantuml.jar***.

With the markup saved as a plain text file, e.g. ***StateDiagram.txt***, generate the rendered diagram using a command like this:



```
java -jar <path to plantuml.jar> <path to spec file>
```



There are options to produce alternative output formats, e.g. .svg

Where can I find this magic jar file you ask?

### **Project's Official Website** ###

- [PlantUML Home](https://plantuml.com/)
- [Quick Start](https://plantuml.com/starting)
- [Quick Start](https://plantuml.com/starting)
- [Edit Diagrams on the Web](http://www.plantuml.com/plantuml/uml/SyfFKj2rKt3CoKnELR1Io4ZDoSa70000)

---
>**The site linked below is a MUCH more useful and aesthetically appealing guide to using PlantUML than the official home page** 
>
>[Welcome to The Hitchhiker’s Guide to PlantUML!](https://crashedmind.github.io/PlantUMLHitchhikersGuide/)

---

### **Other Useful Sites** ###
- [GitHub UML Server](https://github.com/plantuml/plantuml-server)
  - Set up your own PlantUML server, easiest to use the Docker option










