# C# Code Convension

## Class
* Do use Pascal case for a name of a class.
```csharp
public class SampleClassName
{
  // Code.
}
```
* Do not use prefix C or other ones for a name of a class.
```csharp
// Correct.
public interface SampleInterfaceName
{
  // Code.
}

// Incorrect.
public interface CSampleInterfaceName
{
  // Code.
}
```
* Do use a modifier for a class always.
```csharp
// Correct.
public class SampleClassName
{
  // Code.
}

// Correct.
internal class SampleClassName
{
  // Code.
}

// Incorrect.
class SampleClassName
{
  // Code.
}
```

## Interface
* Do use prefix I for a name of an interface.
```csharp
// Correct.
public interface ISampleInterfaceName
{
  // Code.
}

// Incorrect.
public interface SampleInterfaceName
{
  // Code.
}
```
* Do use Pascal case for a name of an interface.
* Do use a modifier for an interface always.
```csharp
// Correct.
public interface ISampleInterfaceName
{
  // Code.
}

// Correct.
internal interface ISampleInterfaceName
{
  // Code.
}

// Incorrect.
interface ISampleInterfaceName
{
  // Code.
}
```

## Constants
* Do use Pascal case for a name of a constant.
```csharp
// Correct.
public const int DefaultPageSize = 10;
public const int StartPage = 0;

// Incorrect
public const int _defaultPageSize = 10;
public const int START_PAGE = 0;
```

## Fields
* Do use prefix _ for a name of a field.
* Do not use prefix m_ or other ones for a name of a field.
* Do use Camel case for a name of a field.
```csharp
// Correct.
private readonly int _pageNo;
private readonly int _total;
private readonly string _title;

// Incorrect.
private readonly int PageNo;
private readonly int total;
private readonly string m_title;
```
* Do not use *public* or *internal* fields.

## Naming
* Do use Pascal case for a class, an interface, a property, a method, and a constant.
```csharp
// Correct.
public abstract class PageDtoBase
{
  private const int DefaultPageSize = 10;
  private const int StartPage = 0;

  public int PageSize { get; set; } = PageDtoBase.DefaultPageSize;

  public int PageNo { get; set; } = PageDtoBase.StartPage;

  public virtual void Clear()
  {
    PageSize = PageDtoBase.DefaultPageSize;
    PageNo = PageDtoBase.StartPage;
  }
}

// Incorrect.
public abstract class PageDtoBase
{
  private const int _defaultPageSize = 10;
  private const int START_PAGE = 0;

  public int pageSize { get; set; } = PageDtoBase._defaultPageSize;

  public int pageNo { get; set; } = PageDtoBase.START_PAGE;

  public virtual void Clear()
  {
    pageSize = PageDtoBase._defaultPageSize;
    pageNo = PageDtoBase.START_PAGE;
  }
}
```
* Do prefix an interface with letter I.
```csharp
// Correct.
public interface IInterface
{
  // Code.
}

// Incorrect.
public interface Interface
{
  // Code.
}
```
* Do use Camel case for a field, a parameter, and a variable.
```csharp
// Correct.
var abc = "abc";
var print = () => Console.WriteLine(abc);

// Incorrect.
var Abc = "abc";
var Print = () => Console.WriteLine(abc);

// Correct.
public sealed class Sample
{
  private string _abc = "abc";

  public void Print(string abc)
  {
    Console.WriteLine(abc);
  }
}

// Incorrect.
public sealed class Sample
{
  private string _Abc = "abc";

  public void Print(string Abc)
  {
    Console.WriteLine(Abc);
  }
}
```
* Do use Pascal case for an acronym.
```csharp
// Correct.
public sealed class DbOptions
{
  // Code.
}

// Incorrect.
public sealed class DBOptions
{
  // Code.
}
```
* Do not use the CLR type names to define a type of a variable, a parameter, a field etc.
```csharp
// Correct.
public sealed class Sample
{
  private readonly int _field;

  public Sample(int field)
  {
    _field = field;
  }

  public int Field { get { return _field; } }
}

// Incorrect.
public sealed class Sample
{
  private readonly Int32 _field;

  public Sample(Int32 field)
  {
    _field = field;
  }

  public Int32 Field { get { return _field; } }
}
```

## Comments
* Do start a comment at a new line, not at the end of a line of code.
* Do start a comment with an uppercase letter.
* Do end a comment with a period.
* Do add one space between delimiter *//* and a text.
```csharp
// It is a first line of a right comment.
// It is a second line of a right comment.
```
* Do not add a space betwee a tag and a text in a doc comment.
```csharp
// Correct.
/// <summary>Represents detail of an entity.</summary>
public class Entity
{
  // Code.
}

// Incorrect.
/// <summary> Represents detail of an entity. </summary>
public class Entity
{
  // Code.
}
```
* Do add a doc comment for each public class, constructor, method, and property.
* Do start a doc comment for a class, method, and property with a third person singular present verb.
```csharp
// Correct.
/// <summary>Provides a simple API.</summary>
public sealed class SampelService
{
  // Code.
}

// Incorrect.
/// <summary>Provide a simple API.</summary>
public sealed class SampelService
{
  // Code.
}

// Incorrect.
/// <summary>A class that provides a simple API.</summary>
public sealed class SampelService
{
  // Code.
}

// Incorrect.
/// <summary>An object that provides a simple API.</summary>
public sealed class SampelService
{
  // Code.
}
```
* Do use a sample below for a comment of a constructor.
```csharp
public sealed class Sample
{
  /// <summary>Initializes a new instance of the <see cref="Sample"/> class.</summary>
  public Sample()
  {
    // Code.
  }
}
```
* Do start a comment for a property with *Gets a value that represents*, *Gets/sets a value that represents* or *Gets or sets a value that represents*, *Gets or sets an object that represents* or *Gets or sets an object that represents*.
```csharp
/// <summary>Represents a base of an entity.</summary>
public abstract class EntityBase
{
  /// <summary>Gets/set a value that represents an ID of an entity.</summary>
  public Guid Id { get; set; }

  /// <summary>Gets/sets an object that represents an instance of the <see cref="InfoEntity" /> class. </summary>
  public InfoEntity Info { get; set; }
}
```

# Attributes
* Do use one line for one attribute.
```csharp
// Correct.
public sealed class SampleDto
{
  [Required]
  [MaxLength(10)]
  public string Property { get; set; }
}

// Incorrect.
public sealed class SampleDto
{
  [Required, MaxLength(10)]
  public string Property { get; set; }
}
```
* Do not use full attribute name. Do use a full name only for attribute class definition.
```csharp
// Correct.
public sealed class SampleDto
{
  [Required]
  public string Property { get; set; }
}

// Incorrect.
public sealed class SampleDto
{
  [RequiredAttribute]
  public string Property { get; set; }
}
```

## LINQ
* Do use only extension methods to build LINQ chains.
```csharp
// Correct.
orders.Where(order => order.Enabled)
      .OrderBy(order => order.Created)
      .FirstOrDefault();

// Incorrect.
(from order in orders
where order.Enabled
orderby order.Created).FirstOrDefault();
```
* Do favour a valuable LINQ parameter name over a short one.
```csharp
// Correct.
var order = orders.Where(order => order.Enabled)
                  .OrderBy(order => order.Created)
                  .FirstOrDefault();

// Incorrect.
var order = orders.Where(x => x.Enabled)
                  .OrderBy(x => x.Created)
                  .FirstOrDefault();
```

# Formatting

* Do add an empty line in an end of a file.
* Do turn on showing white spaces (VS: ctrl+R, ctrl+W).
* Do add an empty line between properties, methods, and constructors.
```csharp
// Correct.
public sealed class SampleService
{
  public SampleService() {}

  public SampleService(
    ISampleRepository0 sampleRepository0,
    ISampleRepository1 sampleRepository1,
    ISampleRepository2 sampleRepository2,
    HttpClient httpClient)
  {
    // Code.
  }

  public int Property0 { get;set; }

  public int Property1 { get;set; }

  public void Method() {}
}

// Incorrect.
public sealed class SampleService
{
  public SampleService() {}
  public SampleService(
    ISampleRepository0 sampleRepository0,
    ISampleRepository1 sampleRepository1,
    ISampleRepository2 sampleRepository2,
    HttpClient httpClient)
  {
    // Code.
  }

  public int Property0 { get;set; }
  public int Property1 { get;set; }
  public void Method() {}
}
```
* Do add an empty line between groupes of fields only.
```csharp
// Correct.
public sealed class SampleService
{
  private readonly ISampleRepository0 _sampleRepository0;
  private readonly ISampleRepository1 _sampleRepository1;
  private readonly ISampleRepository2 _sampleRepository2;

  private readonly HttpClient _httpClient;
}

// Correct too.
public sealed class SampleService
{
  private readonly ISampleRepository0 _sampleRepository0;
  private readonly ISampleRepository1 _sampleRepository1;
  private readonly ISampleRepository2 _sampleRepository2;
  private readonly HttpClient _httpClient;
}

// Incorrect.
public sealed class SampleService
{
  private readonly ISampleRepository0 _sampleRepository0;

  private readonly ISampleRepository1 _sampleRepository1;

  private readonly ISampleRepository2 _sampleRepository2;

  private readonly HttpClient _httpClient;
}
```
* Do not use an empty line in an end or a start of class, method etc.
```csharp
// Correct.
public sealed class SampleClass
{
  public void Method()
  {
    Metho0();
    Metho1();
  }

  public void Method0()
  {
    // Code.
  }

  public void Method1()
  {
    // Code.
  }
}

// Incorrect.
public sealed class SampleClass
{
  public void Method()
  {

    Metho0();
    Metho1();

  }

  public void Method0()
  {
    // Code.
  }

  public void Method1()
  {
    // Code.
  }

}
```
* Do group code in methods, properties, and constructors.
* Do add an empty line between group. Do not add multiple lines.
* Do use logical block *#ifdef* to configure code for an environment.
* Do use logical block *#region* to group fields, properties, constructors etc. that have many lines that cannot be collapsed.
```csharp
// you can collapse the region, but the long constructor.
public sealed class SampleService
{
  #region Constructors

  public SampleService(
    ISampleRepository0 sampleRepository0,
    ISampleRepository1 sampleRepository1
    ISampleRepository2 sampleRepository2
    ISampleRepository3 sampleRepository3
    ISampleRepository4 sampleRepository4)
    {
      // Code.
    }

  #endregion
}
```
* Do split usings to three logical blocks: microsoft, third-party, proj. Do sort usings alphabeticaly in a block.
```csharp
// Correct.
using System;
using System.Threading;
using System.Threading.Tasks;

using Microsoft.AspNetCore.Http;
using Microsoft.AspNetCore.Mvc;

using Project;
using Project.Core;

// Incorrect.
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
// Correct.
public enum Color
{
  White = 0,
  Red = 1,
}

var foo = new Foo
{
  Boo = 123,
};

// Incorrect.
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
* Do not keep any commented out code.
* Do use braces for each *if*, *for* etc.
* Do use the order for members of a class. First order by groups: costants, static members, fields, constructors, properties and methods. Then order in groups by modifier: public, internal, protected internal, protected and private.
* Do use 2 spaces per a tab (VS: Tools->Text Editor->All Languages->Tabs).
* Do put the usings block inside a namespace block.
```csharp
// Correct.
namespace Foo
{
  using System;

  public class Boo
  {
    public Guid Id { get;set; }
  }
}

// Incorrect.
using System;

namespace Foo
{
  public class Boo
  {
    public Guid Id { get;set; }
  }
}
```
* Do add the copyright block in a top of each file. For an example:

## Other

* Do not use this if is is not required.
```csharp
// Correct.
public class Foo
{
  private readonly int _boo;

  public Foo(int boo)
  {
    _boo = boo;
  }
}

// Incorrect.
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
// Correct.
public class Foo
{
  private readonly int _boo;
}

// Incorrect.
public class Foo
{
  private readonly int boo;
}
```
* Do not use *public* or *internal* fields.
```csharp
// Correct.
public class Foo
{
  private int _field0;
  protected int _field1;
}

// Incorrect.
public class Foo
{
  public int _field0;
  internal int _field1;
}
```
* Do use the *sealed* modifier to each classes, except a case when you are going to inherit a class from it exactly.
* Do not use the Enam postfix for a name of an enum.
```csharp
// Correct.
public enum Color
{
  White = 0,
  Red = 1,
}

// Incorrect.
public enum ColorEnum
{
  White = 0,
  Red = 1,
}
```
* Do use a single noun as a name of an enum.
```csharp
// Correct.
public enum Color
{
  White = 0,
  Red = 1,
}

// Incorrect.
public enum Colors
{
  White = 0,
  Red = 1,
}
```
* Do inherit an enum from *byte*, *int* etc. Prefer *byte*.
```csharp
// Correct.
public enum Color : byte
{
  White = 0,
  Red = 1,
}

// Incorrect.
public enum Color
{
  White = 0,
  Red = 1,
}
```
* Do assign a default value for an enum.
```csharp
// Correct.
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

// Incorrect.
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
// Correct.
internal class Foo
{
  private int _boo;
}

// Incorrect.
class Foo
{
  int _boo;
}
```
* Do not create a class, a method etc. which name is long than 30 characters.
* Do name a file the same as a class, an interface etc. in the file.
* Do refactor a method if there are more than 25 lines in the method.
* Do prefer using basic classes/interfaces instead concrete ones. *IList<T>* instead *List<T>*, *IEnumerable<T>* instead *IList<T>* etc.
* Do prefer using arrays instead collections which have no max length.
* Do call a static member/constant with a class name.
```csharp
// Correct.
public abstract class PageDtoBase
{
  private const int DefaultPageSize = 10;
  private const int StartPage = 0;

  public int PageSize { get; set; } = PageDtoBase.DefaultPageSize;

  public int PageNo { get; set; } = PageDtoBase.StartPage;
}

// Incorrect.
public abstract class PageDtoBase
{
  private const int DefaultPageSize = 10;
  private const int StartPage = 0;

  public int PageSize { get; set; } = DefaultPageSize;

  public int PageNo { get; set; } = StartPage;
}
```
* Do use postfix *Base* for an abstract class.
```csharp
public abstract class DtoBase
{
  /// Code.
}
```
* Do not create a constructor with more than 7 parameters.
