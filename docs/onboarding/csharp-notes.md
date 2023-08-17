# C# Notes
### Basic Code Structure

```csharp
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

<br>

### Basic Data Types

```csharp
string characterName = "Zelda";  # strings in double quotes
char characterRank = 'A';        # char in single quote
int characterAge = 1;
bool isMale = true;              # small caps true/false

## to represent decimal numbers:
float                            # least precise
double
decimal                          # most precise (usually used for storing stuff like money, etc.)
```

<br>

### Strings

```csharp
string literalStr = "\nThis will print a new line";

string verbatimStr = @"\nThis will not print new line";             # verbatim string
string winPath = @"C:\Users\path\to\file";                          # mostly used to use escape sequences w/o escaping it in one line
string linkTag = @"<link rel=""stylesheet"" src=""path/to/css"">";  # eg. to represent " within a string

string rawStr = """                                                 # raw string (multi-line to use unescaped escape sequences)
  This is a raw string.                                             # out-indenting delimeter is invalid raw string:
  Lines cannot out-indent                                           #   This raw string will throw an error
  the delimeter                                                     #     """;
""";                                                                # notice that delimeter """ is it's own line
string jsonStr = $"""
  [
    {
      "id": 1,                                                      # raw strings are best used for representing json/xml/html
      "first_name": {faker.Name.FirstName()},                       # example usage using Bogus library (C# port of faker.js)
      "last_name": {faker.Name.LastName()},
      "email": {faker.Internet.Email()},
      "mobile_number": {faker.Phone.PhoneNumber()}
    }
  ]
""";


char[] helloChars = { 'h', 'e', 'l', 'l', 'o' };
string helloStr = new string(helloChars);                          # friendly reminder that string is just an array of chars
string repeatedChar = new string('c', 20);                         # create a string with char repeated x times


# for list of available string props and methods
# see: https://learn.microsoft.com/en-us/dotnet/api/system.string?view=net-7.0#properties
# eg:
string phrase = "hello";
phrase.Length;                                                     # returns string length
phrase.Contains("El");                                             # returns bool (case-sensitive)
# some more examples: ToLower(), ToUpper(), IndexOf(<char>), Substring(<int: start_index>, <Optional[int]: substring_length>)


# for list of available char props and methods
# see: https://learn.microsoft.com/en-us/dotnet/api/system.char?view=net-7.0#fields
# eg:
char firstCharInPhrase = phrase[0];
Console.WriteLine(Char.IsLower(firstCharInPhrase));                 # as to why we can't just do firstCharInPhrase.IsLower(), don't ask me why


(string firstName, string lastName) profile = (firstName: "John", lastName: "Doe");
string fullName = $"{profile.firstName} {profile.lastName}";        # string interpolation
fullName = $@"C:\Users\{profile.firstName}\path\to\file"            # verbatim string interpolation, can also be @$"<string>"

(int X, int Y) coordinate = (X: 2, Y: 3);
# on raw strings, the number of $ specify the number of {} to start and end interpolation
string coordinateMessage = $$"""Coordinate is {{{coordiate.X}}, {{coordinate.Y}}}""";

DateTime currentDateTime = DateTime.Now;
Console.WriteLine(currentDateTime.ToString("yyyy-MM-dd"));          # format string


# if in need of performance
# see: System.Text.StringBuilder
```
