# Study Guide for Exam 3

1. Structure diagrams in UML focus on the [static] aspects of a system, representing the system's structural components, their attributes, relationships, and hierarchies.

2. Behavior diagrams in UML focus on the [dynamic] aspects, illustrating how the system behaves over time, including processes, state changes, and interactions between components.

1. [Structure] diagrams in UML focus on the static aspects of a system, representing the system's structural components, their attributes, relationships, and hierarchies.

2. [Behavior] diagrams in UML focus on the dynamic aspects, illustrating how the system behaves over time, including processes, state changes, and interactions between components.

3. Behavior diagrams that specifically illustrate how objects communicate or collaborate with each other through messages are classified as [interaction] diagrams.

--- (14)

1. The [Class] diagram is the foundation of object-oriented modeling showing classes, attributes, methods, and relationships.

2. A [Object] diagram provides concrete examples of class structures with snapshots of the system containing actual data.

3. The high-level organization of system elements into cohesive packages with their dependencies is shown in a [Package] diagram.

4. A [Component] diagram displays modular system design showing building blocks and their interfaces with dependencies.

5. The [Composite-Structure] diagram illustrates the internal composition of elements showing how parts collaborate within a class.

6. System implementation planning mapping software artifacts to physical hardware nodes is represented in a [Deployment] diagram.

7. Extensions to UML through custom stereotypes, tagged values, and constraints are created using a [Profile] diagram.

8. A [Sequence] diagram shows object interactions over time using a vertical timeline.

9. A [Communication] diagram focuses on message passing between objects.

10. A [Interaction-Overview] diagram combines elements of activity diagrams and sequence diagrams to provide an overview of the control flow.

11. The [Timing] diagram shows state changes of objects with respect to time.

12. A [Use-Case] diagram captures system requirements and user interactions with the system.

13. The [Activity] diagram models workflows, algorithmic logic, and business processes using a flowchart-like notation.

14. A [State-Machine] diaram depicts the different states an object can have and the transitions between those states.

--- (4)

1. In UML class diagrams, the symbol representing public visibility is [+].

2. In UML class diagrams, the symbol representing private visibility is [-].

3. In UML class diagrams, the symbol representing protected visibility is [#].

4. In UML class diagrams, the symbol representing package (default) visibility is [~].

--- (3)

1. In UML class diagrams, abstract classes appear as class rectangles with the class name in [italics].

2. In UML class diagrams, interfaces appear as class rectangles with the stereotype [«interface»] labeled above the interface name.

3. In UML class diagrams, a data type defining a fixed set of named constants is represented using the [<<enumeration>>] stereotype.

--- (6)

1. In UML diagrams, a solid line with a hollow triangle arrowhead pointing toward a more general element represents a(n) [generalization] relationship.  

2. In UML diagrams, a dashed line with an open arrowhead pointing toward the element being implemented or provided represents a(n) [realization] relationship.  

3. In UML diagrams, a solid line connecting elements, possibly including multiplicities, indicating a structural relationship, is called a(n) [association] relationship.  

4. In UML diagrams, a solid line ending with an empty (hollow) diamond at the whole element indicates a(n) [aggregation] relationship, representing a weak whole-part connection.  

5. In UML diagrams, a solid line ending with a filled (solid) diamond at the whole element indicates a(n) [composition] relationship, representing a strong whole-part connection.  

6. In UML diagrams, a dashed line with an open arrowhead pointing from a dependent element to the element it temporarily relies on represents a(n) [dependency] relationship.  

--- (4)

1. In UML relationships, [Composition] represents a strong "has-a" relationship where the part cannot exist independently of the whole (it has the same lifecycle as the whole).

2. In UML relationships, [Aggregation] represents a weak "has-a" relationship where the part can exist independently of the whole (it has its own lifecycle). 

3. In object-oriented programming, the UML concept of generalization is called [inheritance], which occurs when a subclass extends the functionality of a superclass.

4. In object-oriented programming, the UML concept of realization is called [implementation], which occurs when a class provides concrete definitions for methods declared in an interface.

--- (1)

In UML, a [stereotype] is an extension mechanism used to assign additional meaning or specialized roles to elements, typically represented as a name enclosed within guillemets (« »).

--- (5)

1. In UML, [multiplicity] describes how many instances of one element can be connected to an instance of another element through a given association. This relation is often expressed as a string showing the lower and upper bounds at the endpoints of a connection.

2. In UML, the multiplicity [1] indicates "exactly one."

3. In UML, the multiplicity [0..1] indicates "zero or one."

4. In UML, the multiplicity [0..*] indicates "zero or more."

5. In UML, the multiplicity [1..*] indicates "one or more."

--- (2)

7. In UML, interface methods are depicted without implementation details because interfaces cannot include [concrete] method implementations.

2. An interface defines a [contract] that implementing classes must fulfill by specifying methods they are required to implement.

--- (14)

1. The [Joel] Test is a simple 12-question test developed by Spolsky to rate the quality of a software development team.

2. The Joel Test is a simple [12]-question test developed by Spolsky to rate the quality of a software development team.

4. [Hallway] usability testing involves grabbing the next person that passes by and having them try out your software.

5. According to the Joel Test, a score of [10] or lower indicates significant issues in the software development process.

6. [Zero-defect] methodology means that at any given time, the highest priority is to eliminate bugs before writing any new code.

7. In software development economics, [people] are the most significant cost component of the development process.

8. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should have at least one [tester] for every two or three developers to ensure proper quality control.

9. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should implement [daily] builds to catch integration errors quickly.

10. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should have a [spec] that is detailed enough for developers to write code from without requiring additional clarification.

11. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should maintain a [schedule] that is realistic and consistently adhered to throughout the project.

12. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should be able to build their entire software product in [one] step to simplify the build process.

13. According to Joel Spolsky's "Joel Test" for evaluating software teams, high-quality development organizations should use [version] control systems to track all code changes and facilitate collaboration.

14. According to Joel Spolsky's "Joel Test" for evaluating software teams, you should buy the best [tools] money can buy to ensure productivity and quality.

--- (7)

1. Requirements are a description of [what] a system should do, and importantly, they are not a description of [how] the system should do it.

2. In software engineering, [functional] requirements define what a product should do, specify what it should not do, and can be verified individually.

3. In software engineering, [non-functional] requirements describe properties of the system as a whole and are also known as "Quality Requirements."

4. In software engineering, [constraints] restrict how the system must be designed or implemented, limiting the options available to developers.

5. In requirements engineering, [elicitation] is the process of gathering requirements from stakeholders, often through interviews, surveys, or observations.

6. In requirements engineering, [validation] confirms that the requirements correctly reflect the stakeholders' actual needs and intentions. It answers the question, "Are we building the right system?" by ensuring the requirements are consistent, complete, and aligned with business objectives.

7. In requirements engineering, [verification] confirms that the system has been built according to the specified requirements. It answers the question, "Did we build the system right?" by ensuring the implementation accurately follows what was specified.