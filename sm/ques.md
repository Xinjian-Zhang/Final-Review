### System Modelling Questions

#### Q1

**What steps constitute a software development methodology? What questions are expected to be answered by them? What models are expected to answer those questions?** 



A1:

Software development methodologies are structured processes used for planning, creating, testing, and deploying software applications. Each step in a methodology aims to answer specific questions and is supported by different models.

1. **Requirement Gathering and Analysis**:
   - Questions: What does the user need? What problems are we solving?
   - Models: Use case diagrams and user stories help to identify and document user requirements and scenarios.
2. **System Design**:
   - Questions: How will the system meet the identified requirements? What will the system architecture look like?
   - Models: Class diagrams, sequence diagrams, and architecture diagrams are used to outline the system's structure and interactions.
3. **Implementation or Coding**:
   - Questions: How will the design be translated into a working system? What coding standards and practices will be used?
   - Models: While this step is more about coding, UML class diagrams and sequence diagrams can be referenced for implementation guidance.
4. **Testing**:
   - Questions: Does the system meet the requirements? Are there any defects or issues?
   - Models: Test case diagrams and activity diagrams can be used to plan and document testing scenarios and workflows.
5. **Deployment**:
   - Questions: How will the system be deployed into the live environment? What are the deployment procedures?
   - Models: Deployment diagrams provide a view of how the software interacts with the hardware and network environment.
6. **Maintenance**:
   - Questions: How will the system be maintained and updated over time? How will user feedback be incorporated?
   - Models: While maintenance often involves revisiting earlier models and diagrams, it primarily focuses on iterative development and improvement based on user feedback.

----

#### Q2

**What are the two types of class models? What is the purpose of each and what are the differences between them? At which steps is their development expected? Provide a simple example of a class diagram.**



A2:

The two types of class models in software development are:

1. **Domain Class Models**:
   - Purpose: Represent the conceptual model of the domain being addressed by the software. It shows the various entities, their attributes, and relationships in the problem domain, not focusing on software implementation details.
   - Development Stage: Typically developed during the requirements analysis and system design phase to ensure a clear understanding of the domain.
2. **Application Class Models**:
   - Purpose: Represent the classes that will be implemented in the software. This includes not only the entities but also the specific methods and interfaces that will be used in the software implementation.
   - Development Stage: Developed during the detailed design phase, where the focus shifts from the problem domain to the specifics of software implementation.

Differences:

- Domain class models are more abstract, focusing on the real-world entities and their relationships, while application class models are concrete, focusing on the software implementation aspects, including methods and software architecture.

Example of a Simple Class Diagram:

- Consider a basic library system:
  - A "Book" class with attributes like title, author, and ISBN.
  - A "Member" class with attributes like memberID, name, and address.
  - A relationship between "Book" and "Member" indicating which member has borrowed which book.

This class diagram provides a visual overview of the entities involved and their relationships, which is crucial for both understanding the domain and planning the software design.

----

#### Q3

**What is the purpose of aggregation and composition in class diagrams? And how are they different? Provide an example for each of them.**



A3:

Aggregation and composition are two types of relationships in class diagrams used in object-oriented modeling. They represent different levels of association between objects:

1. **Aggregation**:
   - Purpose: Represents a "has-a" or "whole-part" relationship but with less coupling. It implies that the child can exist independently of the parent.
   - Difference: In aggregation, the lifecycle of the part does not depend on the lifecycle of the whole. The part can be shared between different wholes.
   - Example: Consider a "Library" class and a "Book" class. The library has books, but the books can exist independently of the library. If the library closes, the books still exist.
2. **Composition**:
   - Purpose: Represents a stronger form of the "whole-part" relationship. It implies ownership, where the part cannot exist independently of the whole.
   - Difference: In composition, the lifecycle of the part is tied to the lifecycle of the whole. If the whole is destroyed, the parts are also destroyed. The part cannot belong to more than one whole.
   - Example: Consider a "House" class and a "Room" class. A room is part of a house and cannot e

----

#### Q4

**What is the purpose of an enumeration in class diagrams? How is it different from generalization? Provide an example for each of them.**



A4:

In class diagrams:

1. **Enumeration**:
   - Purpose: Enumeration is used to define a type that can have one of a finite set of values. These values are named constants and are explicitly defined. Enumeration ensures that a variable can only be assigned one of the predefined constants, enhancing readability and maintainability of the code.
   - Difference from Generalization: Enumeration does not involve hierarchy or inheritance. It's simply a list of predefined values.
   - Example: Consider an enumeration for days of the week: `enum Day { Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday }`. This enumeration specifies that a variable of type `Day` can only hold one of these seven values.
2. **Generalization**:
   - Purpose: Generalization is used to represent an inheritance relationship in object-oriented modeling. It signifies that a subclass inherits attributes and methods from a superclass, allowing for reuse and extension of behavior.
   - Difference from Enumeration: Generalization involves a hierarchy between a more general (superclass) and a more specific (subclass) class. It's about behavior and attributes inheritance, not about defining a set of values.
   - Example: Consider a general class `Vehicle` with subclasses `Car` and `Bicycle`. Both `Car` and `Bicycle` inherit properties from `Vehicle` (like speed, or capacity) but also have their own specific attributes.

Enumeration and generalization serve distinct purposes in class diagrams. While enumeration defines a fixed set of values, generalization defines a hierarchical relationship between classes. Both are essential tools in object-oriented modeling for different reasons.



----

#### Q5

**What is derived data in a class diagram? What is the benefit of having it? Provide an example of derived data.**



A5:

Derived data in a class diagram refers to an attribute that is calculated or derived from other attributes, rather than being stored directly. This concept is used in object-oriented modeling to represent values that can be computed from existing data.

**Benefits of Derived Data:**

1. **Reduces Data Redundancy**: By calculating data on the fly, it eliminates the need to store and manage duplicate information.
2. **Ensures Consistency**: Derived data ensures that the calculated value is always current and consistent with the source data, avoiding synchronization issues.
3. **Efficiency in Data Management**: It can make updates more efficient, as only the source data needs to be updated, and the derived data gets automatically recalculated.

**Example of Derived Data:** Consider a class `Person` with attributes `dateOfBirth` (a stored attribute) and `age` (a derived attribute). The `age` of the person is not stored directly but is derived from the current date and their `dateOfBirth`. In UML, this would be indicated by placing a slash before the derived attribute, like `/age`.

In this example, `age` is derived and updated based on the `dateOfBirth` and the current date, ensuring that it's always accurate without needing to store or manually update the age attribute.

----

