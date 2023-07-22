Write a program that will calculate the number of trailing zeros in a factorial of a given number.

N! = 1 * 2 * 3 *  ... * N

Be careful 1000! has 2568 digits...

For more info, see: http://mathworld.wolfram.com/Factorial.html

Examples:
```
zeros(6) = 1
# 6! = 1 * 2 * 3 * 4 * 5 * 6 = 720 --> 1 trailing zero

zeros(12) = 2
# 12! = 479001600 --> 2 trailing zeros
```
Hint: You're not meant to calculate the factorial. Find another way to find the number of zeros.
***
Solution:
```c#
using System;

public static class Kata 
{
  public static int TrailingZeros(int n)
  {
    int trailing = 0;
    for(var i = 1; i <= n; i++)
    {
      int divide = n / (int)Math.Pow(5, i);
      trailing += divide;
      if(divide <= 1)
      {
        break;
      }
    }
    return trailing;
  }
}
```
References:
- [Math.Pow](https://learn.microsoft.com/en-us/dotnet/api/system.math.pow)
- [Casting and type conversions](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
