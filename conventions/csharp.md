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

## Enums (frequently misunderstood ;) ) 
* Naming conventions
  * Use Pascal case for Enum types and value names.
  * Use abbreviations sparingly.
  * Do not use an Enum suffix on Enum type names.
  * Use a singular name for most Enum types, but use a plural name for Enum types that are bit fields.
  * Always add the FlagsAttribute to a bit field Enum type.
* Enum design (https://msdn.microsoft.com/en-us/library/ms229058(v=vs.110).aspx)
