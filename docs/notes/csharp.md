# C# Notes

## Basic Code Structure

=== "Basic Skeleton"

    ```csharp linenums="1"
    using <Namespace.Class.Method>;
    ...

    namespace <Namespace>
    {
        <access_modifier> class <Class>
        {
            <access_modifier> <return_type> <Method>(<type> param)
            {
                ...
            }
        }
    }
    ```

=== "Sample Code"

    ```csharp linenums="1"
    using System;

    namespace Greeting
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Hello World");
            }
        }
    }
    ```

## Basic Data Types

```csharp linenums="1"
string characterName = "Zelda";  // strings in double quotes
char characterRank = 'A';        // char in single quote
int characterAge = 100;
bool isMale = false;             // small caps true/false

// to represent decimal numbers:
float                            // least precise
double
decimal                          // most precise (1)
```

1. usually used for storing stuff like money, etc.

## Strings

### Literal Strings

```csharp linenums="1"
string literalStr = "\nThis will print a new line";
```

### Verbatim Strings

Mostly used to use unescaped sequences in one line.

```csharp linenums="1"
string verbatimStr = @"\nThis will not print new line";
string winPath = @"C:\Users\path\to\file";
string linkTag = @"<link rel=""stylesheet"" src=""path/to/css"">";
```

### Raw Strings

Multi-line use of unescaped escape sequences.

```csharp linenums="1"
string rawStr = """
  This is a raw string.
  Lines cannot out-indent // (1)!
  the delimeter
""";                       // notice that the delimeter """ is it's own line

// raw strings are best used for representing json/xml/html
// example usage using Bogus library (C# port of faker.js)
string jsonStr = $"""
  [
    {
      "id": 1,
      "first_name": {faker.Name.FirstName()},
      "last_name": {faker.Name.LastName()},
      "email": {faker.Internet.Email()},
      "mobile_number": {faker.Phone.PhoneNumber()}
    }
  ]
""";
```

1. out-indenting delimeter is invalid raw string:
    ```csharp
    string rawString="""
    This raw string will throw an error
        """;
    ```

### Props and Methods

```csharp linenums="1"
// for list of available string props and methods
// see: https://learn.microsoft.com/en-us/dotnet/api/system.string?#properties
string phrase = "hello";
phrase.Length;           // returns string length
phrase.Contains("El");   // returns bool (case-sensitive)
// some more examples: ToLower(), ToUpper(), IndexOf(<char>),
// Substring(<int: start_index>, <Optional[int]: substring_length>)
```

### String Interpolation

```csharp linenums="1"
(string firstName, string lastName) profile = (firstName: "John", lastName: "Doe");
string fullName = $"{profile.firstName} {profile.lastName}";
fullName = $@"C:\Users\{profile.firstName}\path\to\file";  // can also be @$

(int X, int Y) coord = (X: 2, Y: 3);
string coordMessage = $$"""Coordinate is {{{coordiate.X}}, {{coordinate.Y}}}"""; // (1)!
```

1. on raw strings, the number of `$` specify the number of `{` `}` to start and end interpolation

### Format String

```csharp linenums="1"
DateTime currentDateTime = DateTime.Now;
Console.WriteLine(currentDateTime.ToString("yyyy-MM-dd"));
```

### Chars

```csharp linenums="1"
char[] helloChars = { 'h', 'e', 'l', 'l', 'o' };
// friendly reminder that string is just an array of chars
string helloStr = new string(helloChars);
// create a string with char repeated x times
string repeatedChar = new string('c', 20);
```
#### Props and Methods

```csharp linenums="1"
// for list of available char props and methods
// see: https://learn.microsoft.com/en-us/dotnet/api/system.char?#fields
char firstCharInPhrase = phrase[0];
Console.WriteLine(Char.IsLower(firstCharInPhrase)); // (1)!
```

1. as to why we can't just do `firstCharInPhrase.IsLower()`, don't ask me why

### String Builder

```csharp linenums="1"
// if in need of performance
// see: System.Text.StringBuilder
```
