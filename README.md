# C# Code Convension

#### 1. Do add an empty line in an end of a file.
#### 2. Do not use multiple lines between ligical blocks. Do use one line.
#### 3. Do not use this if is is not required.
#### 4. Do use the sealed modifier to each classes, except a case when you are going to inherit a class from it exactly.
#### 5. Do not use the Enam postfix for name of enum.
#### 6. Do use one file for one class, interface etc.
#### 7. Do use access modifiers everytime. Do not hope a default access modifier value.
```csharp
//correct
internal class Foo
{
  private int _boo;
}
//incorrect
class Foo
{
  int _boo;
}
```
#### 8. Do add a doc comment for each public or internal class, method and property.
#### 9. Do use one empry line between logical block. Do not use an empty line in an end of class, method etc.
#### 10. Do use logical block #ifdef
#### 11. Do split usings to three logical blocks: microsoft, third-party, proj. Do sort usings alphabeticaly.
#### 12. Do use coma after an enam value.
#### 13. Do not use any commented code.
#### 14. Do not write attributes in one line. Do use one line for one attribute.
#### 15. Do not use full attribute name. Do use a full name only for attribute class definition.
#### 16. Max length of name of file, class, method etc.
#### 17. Do use braces for each if, for etc.
#### 18. Do use the order for members of a class. Costants, static members, fields, constructors, properties and methods. Public, internal, protected internal, protected and private.
#### 19. Do use 2 spaces per tab.
#### 20. usings in namespace.
#### 21. copyright in a top of each file.
#### 22. If a method contans more than 20 lines it is a occasion to refactor this method.
#### 23. Do prefer using basic classes/interfaces instead concrete ones. IList instead List, IEnumerable instead IList.
#### 24. Do prefer using arrays instead collections which have no max length.
#### 25. Do use only extension methods to build LINQ chains.
```csharp
// correct
orders.Where(order => order.Enabled)
      .OrderBy(order => order.Created)
      .FirstOrDefault();
// incorrect
(from order in orders
where order.Enabled
orderby order.Created).FirstOrDefault();
```