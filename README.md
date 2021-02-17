# C# Code Convension

* Do add an empty line in an end of a file.
* Do turn on showing white spaces (VS: ctrl+R, ctrl+W).
* Do not use multiple lines between ligical blocks. Do use one line.
* Do not use this if is is not required.
* Do use the sealed modifier to each classes, except a case when you are going to inherit a class from it exactly.
* Do not use the Enam postfix for a name of an enum.
* Do use a single noun as a name of an enum.
* Do use one file for one class, interface etc.
* Do use access modifiers everytime. Do not hope a default access modifier value.
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
* Do add a doc comment for each public or internal class, method and property.
* Do use one empty line between logical block. Do not use an empty line in an end of class, method etc.
* Do use logical block #ifdef to configure code for an environment.
* Do use logical block #region to group fields, properties, constructors etc. that have many lines that cannot be collapsed.
* Do split usings to three logical blocks: microsoft, third-party, proj. Do sort usings alphabeticaly.
* Do use coma after an enam value.
* Do not use any commented code.
* Do not write attributes in one line. Do use one line for one attribute.
* Do not use full attribute name. Do use a full name only for attribute class definition.
* Max length of name of file, class, method etc.
* Do use braces for each if, for etc.
* Do use the order for members of a class. Costants, static members, fields, constructors, properties and methods. Public, internal, protected internal, protected and private.
* Do use 2 spaces per a tab.
* Do put the usings block inside a namespace block.
* Do add the copyright block in a top of each file.
* If a method contans more than 20 lines it is a occasion to refactor this method.
* Do prefer using basic classes/interfaces instead concrete ones. IList instead List, IEnumerable instead IList.
* Do prefer using arrays instead collections which have no max length.
* Do use only extension methods to build LINQ chains.
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