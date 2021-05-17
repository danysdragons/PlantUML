## **PlantUML - Guide to Basic Usage**

Note: I am **not** the creator of PlantUML, and this repository does not host the source code for PlantUML. This repository is just intended _to illustrate basic usage of PlantUML_.

PlantUML provides a declarative syntax for generating various UML diagrams: class diagrams, sequence diagrams, use case diagrams etc.

An example of the markup for a state transition diagram:

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

![alt text](https://raw.githubusercontent.com/danysdragons/PlantUML-Usage-Examples/master/State%20Diagram/stateDiagram.png "A nice state machine diagram, woot!")

The renderer is distributed as a single Java _jar_ file, **_plantuml.jar_**. The plantuml.jar file is included in this repository for convenience, but you may want to check the PlantUML website for the most up-to-date version.

With the markup saved as a plain text file, e.g. **_StateDiagram.txt_**, generate the rendered diagram using a command like this:

```
java -jar <path to plantuml.jar> <path to diagram specification file>
```

There are options to produce alternative output formats, e.g. .svg. To see all available options:

```
java -jar plantuml.jar -h
```

---

### **Dependency on Graphviz** ###

PlantUML has a dependency on Graphviz and its **dot** executable. For more details, see the link below.

https://plantuml.com/graphviz-dot

\*\*\*Note that when running PlantUML on Windows, installation of Graphviz is no longer required:\*\*\*

>If you use a recent version (that is at least version 1.2020.21), you don't need to manually install GraphViz anymore !
>
>A minimalistic graphviz dot.exe is packed into PlantUML and will be automagically unzipped in some temporary folder 
>
>This is really the prefered option under Windows.

---

### **Project's Official Website**

- [PlantUML Home](https://plantuml.com/)
- [Quick Start](https://plantuml.com/starting)
- [Quick Start](https://plantuml.com/starting)
- [Web Application for Creating PlantUML Diagrams](http://www.plantuml.com/plantuml/uml/SyfFKj2rKt3CoKnELR1Io4ZDoSa70000)

---

> **The site linked below is a MUCH more useful and aesthetically appealing guide to using PlantUML than the official home page**
>
> [Welcome to The Hitchhiker’s Guide to PlantUML!](https://crashedmind.github.io/PlantUMLHitchhikersGuide/)

---

### **Other Useful Sites**

- [GitHub UML Server](https://github.com/plantuml/plantuml-server)
  - Set up your own PlantUML server, with the same functionality as the web application provided by the PlantUML Project's offficial website. Using the Docker version is by far the easiest approach.
