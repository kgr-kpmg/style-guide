## Elementals Coding Guidelines
This file documents the coding styles we think we should all strive to adopt when working on projects with the goal of increasing and maintaining code quality. With good code quality, projects are much more pleasant to work with for everyone.

This document is simply a style guide and is not intended to be a ‘be-all and end-all’. If you think it makes more sense to do something a bit different then go for it. Better yet, consider documenting it here.

### General Style Guide
-	Make use of positive validation when validating user input 
-	Allow access only to those who should have access – deny access by default
-	Store cookies securely with a ticket store
-	Short lived sessions should be stateless
-	Stateful sessions should be invalidated after logout
-	Input should be sanitised to defend against XSS and other injection attacks
-	Log all auditable actions, (i.e. log-in log-out, validation failures) with enough context so that suspicious activity can be identified.
-	Where necessary verify data has not been tampered with and comes from a known trusted source
-	When workings with databases use EF Core

### C#
In general it makes sense to follow Microsoft’s own coding styles for C#: https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions.
Some of the notable points below are also adapted from Google’s C# style guide: https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions

### Formatting
See the [.editorconfig](.editorconfig) file

StyleCop and SonarLint are great tools for linting and formatting C# code. They can be added as either IDE plugins/extensions, or as nuget packages in projects. Using these as nuget packages is a good option because it means that all team members will benefit by default, and will not necessarily need to install an extension.

The two packages are:
 - SonarAnalyzer.CSharp
 - StyleCop.Analyzers

### Coding Styles
Here are some notable points from both Google and Microsoft’s style guides:
 - File names, class names and method names should all be PascalCase
 - Local variables and parameters should be camelCase
 - Private, protected, internal properties should begin with underscore and  _camelCase
 - Interfaces should begin with ‘I’ e.g. ‘IService’
 - Acronyms should be written as ‘MyRpc’ instead of ‘MyRPC’
 - Prefer method syntax for Linq with newline for each chained method where beneficial for readability
 - Use an extension methods where the functionality would make sense in the original source but the original source can't be changed easily.
 - Prefer regular `foreach` over Container.ForEach() except for single line statements
 - Use string interpolation for concatenation except where StringBuilder would provide a noticeable performance improvement.
 - Use const wherever possible
 - Use expression body syntax for single line readonly properties (=>)

### JavaScript

For more general JavaScript and React styling, refer to AirBnB’s guides on GitHub: https://github.com/airbnb/javascript and https://github.com/airbnb/javascript/tree/master/react
These guides make sensible styling decisions straight of the box.

The Prettier extension for VS Code by default does a really good job of formatting code to a good standard. It can be configured to format on save in VS Code. Simply press Ctrl + Shift + P and type ‘Format on save’ and turn on this option in the editor.
