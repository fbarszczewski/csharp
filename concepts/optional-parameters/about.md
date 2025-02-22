# About

A method parameter can be made optional by assigning it a default value. When a parameter is optional, the caller is not required to supply an argument for that parameter, in which case the default value will be used. [Optional parameters][optional-arguments] _must_ be at the end of the parameter list; they cannot be followed by non-optional parameters. If a method has multiple optional parameters, you can specify only some of them using [named arguments][named-arguments].

```csharp
class Card
{
    static string NewYear(int year = 2020, string sender = "me")
    {
        return $"Happy {year} from {sender}!";
    }
}

Card.NewYear();  // => "Happy 2020 from me!"
Card.Card(1999); // => "Happy 1999 from me!"
Card.Card(sender: "mom"); // => "Happy 2020 from mom!"
```

An optional parameter's value must be either:

- A constant expression (e.g. `"hi"`, `2`, `DayOfWeek.Friday`, `null` etc.)
- A `new` expression of a value type
- A `default` expression of a value type

[optional-arguments]: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments#optional-arguments
[named-arguments]: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments#named-arguments
