# C# Code Convension

* Do add an empty line in an end of a file.
* Do turn on showing white spaces (VS: ctrl+R, ctrl+W).
* Do not use this if is is not required.
```csharp
// correct
public class Foo
{
  private readonly int _boo;

  public Foo(int boo)
  {
    _boo = boo;
  }
}

// incorrect
public class Foo
{
  private readonly int boo;

  public Foo(int boo)
  {
    this.boo = boo;
  }
}
```
* Do use prefix _ for a field.
```csharp
// correct
public class Foo
{
  private readonly int _boo;
}

// incorrect
public class Foo
{
  private readonly int boo;
}
```
* Do not use *public* or *internal* fields.
```csharp
// correct
public class Foo
{
  private int _field0;
  protected int _field1;
}

// incorrect
public class Foo
{
  public int _field0;
  internal int _field1;
}
```
* Do use the *sealed* modifier to each classes, except a case when you are going to inherit a class from it exactly.
* Do not use the Enam postfix for a name of an enum.
```csharp
// correct
public enum Color
{
  White = 0,
  Red = 1,
}

// incorrect
public enum ColorEnum
{
  White = 0,
  Red = 1,
}
```
* Do use a single noun as a name of an enum.
```csharp
// correct
public enum Color
{
  White = 0,
  Red = 1,
}

// incorrect
public enum Colors
{
  White = 0,
  Red = 1,
}
```
* Do inherit an enum from *byte*, *int* etc. Prefer *byte*.
```csharp
// correct
public enum Color : byte
{
  White = 0,
  Red = 1,
}

// incorrect
public enum Color
{
  White = 0,
  Red = 1,
}
```
* Do assign a default value for an enum.
```csharp
// correct
public enum Color : byte
{
  White = 0,
  Red = 1,
}
public enum Pet : byte
{
  None = 0,
  Cat = 1,
  Dog = 2,
}

// incorrect
public enum Color : byte
{
  White,
  Red,
}
public enum Pet : byte
{
  Cat = 1,
  Dog = 2,
}
```
* Do use one file for one class, interface etc.
* Do use access modifiers everytime. Do not hope a default access modifier value.
```csharp
// correct
internal class Foo
{
  private int _boo;
}

// incorrect
class Foo
{
  int _boo;
}
```
* Do add a doc comment for each public or internal class, method and property.
* Do use one empty line between logical block. Do not use multiple lines between ligical blocks.
* Do not use an empty line in an end of class, method etc.
* Do use logical block *#ifdef* to configure code for an environment.
* Do use logical block *#region* to group fields, properties, constructors etc. that have many lines that cannot be collapsed.
* Do split usings to three logical blocks: microsoft, third-party, proj. Do sort usings alphabeticaly in a block.
```csharp
// correct
using System;
using System.Threading;
using System.Threading.Tasks;

using Microsoft.AspNetCore.Http;
using Microsoft.AspNetCore.Mvc;

using Project;
using Project.Core;

// incorrect
using Microsoft.AspNetCore.Http;
using Microsoft.AspNetCore.Mvc;
using Project;
using Project.Core;
using System;
using System.Threading;
using System.Threading.Tasks;
```
* Do use a trailing comma.
```csharp
// correct
public enum Color
{
  White = 0,
  Red = 1,
}

var foo = new Foo
{
  Boo = 123,
};

// incorrect
public enum Color
{
  White = 0,
  Red = 1
}

var foo = new Foo
{
  Boo = 123
};
```
* Do not keep any commented old code.
* Do use one line for one attribute.
```csharp
// correct
public sealed SampleDto
{
  [Required]
  [MaxLength(10)]
  public string Property { get; set; }
}

// incorrect
public sealed SampleDto
{
  [Required, MaxLength(10)]
  public string Property { get; set; }
}
```
* Do not use full attribute name. Do use a full name only for attribute class definition.
* Max length of name of file, class, method etc.
* Do use braces for each if, for etc.
* Do use the order for members of a class. Costants, static members, fields, constructors, properties and methods. Public, internal, protected internal, protected and private.
* Do use 2 spaces per a tab.
* Do put the usings block inside a namespace block.
```csharp
// correct
namespace Foo
{
  using System;

  public class Boo
  {
    public Guid Id { get;set; }
  }
}

// incorrect
using System;

namespace Foo
{
  public class Boo
  {
    public Guid Id { get;set; }
  }
}
```
* Do add the copyright block in a top of each file.
* If a method contans more than 20 lines it is a occasion to refactor this method.
* Do prefer using basic classes/interfaces instead concrete ones. *IList<T>* instead *List<T>*, *IEnumerable<T>* instead *IList<T>* etc.
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