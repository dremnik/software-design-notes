SOLID Go Design
---------------

**Single responsibility principle**
* A class should have only one reason to change.
* Decoupled design: this is the *UNIX* design philosophy.
* You combine smaller programs with one responsibility into larger structures.


**Open/Closed Principle**
* Software entities should be open for extension but closed for modification.


**Liskov Substitution Principe**
* Small interfaces lead to simple implementations. ( Think here of the Reader interface.,
	because it is so simple it becomes extremely powerful. )

**Interface Segregration Principle**
* A great rule of thumb for Go is to *accept interfaces, return structs.*


**Dependency Inversion Principle**
* High level modules should not depend on low level modules. Both should
  depend on abstractions.
  Abstractions should not depend on details. Details should depend on abstractions.

Source: [SOLID Go Design | Dave Cheney](https://www.youtube.com/watch?v=zzAdEt3xZ1M)
