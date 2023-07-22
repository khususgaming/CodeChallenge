Return the number (count) of vowels in the given string.

We will consider a, e, i, o, u as vowels for this Kata (but not y).

The input string will only consist of lower case letters and/or spaces.
```c#
public static class Kata
{
    public static int GetVowelCount(string str)
    {
        int vowelCount = 0;

        char[] vowels = {'a', 'i', 'u', 'e', 'o'};
        for(var i = 0; i < vowels.Length; i++)
        {
          for(var j = 0; j < str.Length; j++)
          {
            if(vowels[i] == str[j])
            {
              vowelCount++;
            }
          }
        }

        return vowelCount;
    }
}
```
