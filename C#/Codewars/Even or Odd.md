Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.
```c#
using System;

namespace Solution
{
  public class SolutionClass
  {
    public static string EvenOrOdd(int number)
    {
      int[] even = {0, 2, 4, 6, 8};
      int[] odd = {1, 3, 5, 7, 9};
      
      string numberStr = number.ToString();
      int numberLength = numberStr.Length;
      int numberIndex = (int)Char.GetNumericValue(numberStr[numberLength - 1]);
      
      bool existEven = Array.Exists(even, e => e == numberIndex);
      bool existOdd = Array.Exists(odd, e => e == numberIndex);
      if(existEven)
      {
        return "Even";
      }
      else if(existOdd)
      {
        return "Odd";
      }
      
      return "Neither";
    }
  }
}
```
Reference
- [Char.GetNumericValue](https://learn.microsoft.com/en-us/dotnet/api/system.char.getnumericvalue?view=net-6.0)
- [Array.Exists](https://learn.microsoft.com/en-us/dotnet/api/system.array.exists?view=net-6.0)
