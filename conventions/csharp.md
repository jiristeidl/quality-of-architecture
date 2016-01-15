# C# convetions

## Naming conventions

The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.

## Files and Structure
* **Do not** have more than one public type in a source file, unless they differ only in the number of generic parameters or one is nested in the other.  Multiple internal types in one file are allowed.
* **Do** name the source file with the name of the public type it contains. For example, MainForm class should be in MainForm.cs file and List<T> class should be in List.cs file.

## General Naming Conventions
* **Do use meaning names** for various types, functions, variables, constructs and types.
* You should **not use of shortenings** or contractions as parts of identifier names. For example, use “GetWindow” rather than “GetWin”. For functions of common types, thread procs, window procedures, dialog procedures use the common suffixes for these “ThreadProc”, “DialogProc”, “WndProc”.

## Capitalization Naming Rules for Identifiers
* see "Naming conventions" bellow
* suplements:
  * non-public fields: camelCase or _camelCase (**Do be consistent** in a code sample when you use the '_' prefix.)

## Guidelines
* Capitalization Conventions (https://msdn.microsoft.com/en-us/library/ms229043.aspx)
* .NET Naming conventions (https://msdn.microsoft.com/en-us/library/ms229040(v=vs.110).aspx)
* Naming Assemblies and DLLs (https://msdn.microsoft.com/en-us/library/ms229048(v=vs.110).aspx)
* Names of Namespaces (https://msdn.microsoft.com/en-us/library/ms229026(v=vs.110).aspx)
* Names of Classes, Structs, and Interfaces (https://msdn.microsoft.com/en-us/library/ms229040(v=vs.110).aspx)
* Names of Type Members (https://msdn.microsoft.com/en-us/library/ms229002(v=vs.110).aspx)
* Naming Parameters (https://msdn.microsoft.com/en-us/library/ms229004(v=vs.110).aspx)
* Naming Resources (https://msdn.microsoft.com/en-us/library/ms229037(v=vs.110).aspx)

## Coding conventions

* C# Coding Conventions (https://msdn.microsoft.com/en-us/library/ff926074.aspx)

## Frequent misunderstoodings :)

### Enums 
* Naming conventions
  * Use Pascal case for Enum types and value names.
  * Use abbreviations sparingly.
  * Do not use an Enum suffix on Enum type names.
  * Use a singular name for most Enum types, 
  * Use a plural name for Enum types that are bit fields (flags).
  * Always add the FlagsAttribute to a bit field Enum type.
* Enum design (https://msdn.microsoft.com/en-us/library/ms229058(v=vs.110).aspx)
* Use bitwise operators when evaluating flags enum
* Consider to not store flags in SQL-type databases
* Define flags with bit shift operator to better understand it's values (example bellow) 

```csharp
[Flags]
public enum MyEnum
{
  None = 0,           /*0000000000000000000000000000000*/
  Flag1 = 1 << 0,     /*0000000000000000000000000000001*/
  Flag2 = 1 << 1,     /*0000000000000000000000000000010*/
  Flag3 = 1 << 2,     /*0000000000000000000000000000100*/
  Flag4 = 1 << 3,     /*0000000000000000000000000001000*/
  Flag5 = 1 << 4      /*0000000000000000000000000010000*/
}
```

### Strings 
* **Do** not use the ‘+’ operator to concatenate many strings. Instead, you should use StringBuilder for concatenation. However, do use the ‘+’ operator to concatenate small numbers of strings.
* **Do** use overloads that explicitly specify the string comparison rules for string operations. Typically, this involves calling a method overload that has a parameter of type *StringComparison*.
* **Do** use *StringComparison.Ordinal* or *StringComparison.OrdinalIgnoreCase* for comparisons as your safe default for culture-agnostic string matching, and for better performance. (Do not use constructions like "".ToLower() == "".ToLower())
* **Do** use string operations that are based on StringComparison.CurrentCulture when you display output to the user.
* **Do** use an overload of the String.Equals method to test whether two strings are equal. For example, to test if two strings are equal ignoring the case
* **Do** use an overload of the String.Equals method to test whether two strings are equal. For example, to test if two strings are equal ignoring the case
* **Do** use the String.ToUpperInvariant method instead of the String.ToLowerInvariant method when you normalize strings for comparison.
 
### Fields
* **Do not** provide instance fields that are public or protected. Public and protected fields do not version well and are not protected by code access security demands. Instead of using publicly visible fields, use private fields and expose them through properties. 
* **Do** use public static read-only fields for predefined object instances.
* **Do** use constant fields for constants that will never change.
* **Do not** assign instances of mutable types to read-only fields.
 
## Properties
* **Do** create read-only properties if the caller should not be able to change the value of the property.
* **Do not** provide set-only properties. If the property getter cannot be provided, use a method to implement the functionality instead. The method name should begin with Set followed by what would have been the property name.
* **Do** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or an extremely inefficient design.
* **You should not throw exceptions from property getters**. Property getters should be simple operations without any preconditions. If a getter might throw an exception, consider redesigning the property to be a method. This recommendation does not apply to indexers. Indexers can throw exceptions because of invalid arguments. It is valid and acceptable to throw exceptions from a property setter.
 
## Constructors
* **Do minimal work in the constructor.** Constructors should not do much work other than to capture the constructor parameters and set main properties. The cost of any other processing should be delayed until required.
* **Do** throw exceptions from instance constructors if appropriate.
* **Do not call virtual members on an object inside its constructors.** Calling a virtual member causes the most-derived override to be called regardless of whether the constructor for the type that defines the most-derived override has been called.
 
## Exceptions
* **Do report execution failures by throwing exceptions.** Exceptions are the primary means of reporting errors in frameworks. If a member cannot successfully do what it is designed to do, it should be considered an execution failure and an exception should be thrown. **Do not return error codes.**
* **Do throw the most specific (the most derived) exception that makes sense.** For example, throw ArgumentNullException and not its base type ArgumentException if a null argument is passed. *Throwing System.Exception as well as catching System.Exception are nearly always the wrong thing to do.*
* **Do not use exceptions for the normal flow of control**, if possible. Except for system failures and operations with potential race conditions, you should write code that does not throw exceptions. For example, you can check preconditions before calling a method that may fail and throw exceptions
* Do not throw exceptions from exception filter blocks and (explicitly) from finally blocks.
* **You should not swallow errors by catching nonspecific exceptions, such as System.Exception, System.SystemException**, and so on in .NET code. Do catch only specific errors that the code knows how to handle.  You should catch a more specific exception, or re-throw the general exception as the last statement in the catch block. There are cases when swallowing errors in applications is acceptable, but such cases are rare. 
* **Do** prefer using an empty throw when catching and re-throwing an exception. This is the best way to preserve the exception call stack.
* **DO NOT THROW NEW EXCEPTION("message") IN CATCH BLOCK**, always throw specific exception and include original exception object to preserve stacktrace: **throw new SomethingBadHappendException("message", originalException)**


