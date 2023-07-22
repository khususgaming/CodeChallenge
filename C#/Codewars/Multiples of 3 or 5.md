If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).

Note: If the number is a multiple of both 3 and 5, only count it once.

Courtesy of projecteuler.net (Problem 1)
***
Solution:
```c#
using System;

public static class Kata
{
  public static int Solution(int value)
  {
    if (value < 0) return 0;

    int[] multiples = { 3, 5 };
    int multiplesCount = 0;
    int[] save = new int[value];
    for (var i = 0; i < multiples.Length; i++)
    {
      for (var j = 0; j < value; j++)
      {
        var calc = j * multiples[i];
        if (calc < value)
        {
          bool exist = Array.Exists(save, e => e == calc);
          if (!exist)
          {
            for (var k = 0; k < save.Length; k++)
            {
              if (save[k] == 0)
              {
                save[k] = calc;
                break;
              }
            }
          }
        }
        else 
        {
          break;
        }
      }
    }
    int count = 0;
    for (var i = 0; i < save.Length; i++)
    {
      count += save[i];
    }
    multiplesCount += count;

    return multiplesCount;
  }
}
```
Reference
- [Array.Exists](https://learn.microsoft.com/en-us/dotnet/api/system.array.exists?view=net-6.0)
