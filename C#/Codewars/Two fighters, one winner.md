Create a function that returns the name of the winner in a fight between two fighters.

Each fighter takes turns attacking the other and whoever kills the other first is victorious. Death is defined as having health <= 0.

Each fighter will be a Fighter object/instance. See the Fighter class below in your chosen language.

Both health and damagePerAttack (damage_per_attack for python) will be integers larger than 0. You can mutate the Fighter objects.

Your function also receives a third argument, a string, with the name of the fighter that attacks first.

Example:
```
declare_winner(Fighter("Lew", 10, 2), Fighter("Harry", 5, 4), "Lew") => "Lew"
  
Lew attacks Harry; Harry now has 3 health.
Harry attacks Lew; Lew now has 6 health.
Lew attacks Harry; Harry now has 1 health.
Harry attacks Lew; Lew now has 2 health.
Lew attacks Harry: Harry now has -1 health and is dead. Lew wins.
```
```c#
public class Fighter {
  public string Name;
  public int Health, DamagePerAttack;
  public Fighter(string name, int health, int damagePerAttack) {
    this.Name = name;
    this.Health = health;
    this.DamagePerAttack = damagePerAttack;
  }
}
```
***
Solution:
```c#
public class Kata {
  public static string declareWinner(Fighter fighter1, Fighter fighter2, string firstAttacker) {
    string isWinner = string.Empty;
    if (fighter1.Name == firstAttacker)
    {
      for (var i = fighter1.Health; i >= 0; i = fighter1.Health)
      {
        fighter2.Health -= fighter1.DamagePerAttack;
        if (fighter1.Health >= fighter2.Health && fighter2.Health <= 0)
        {
          isWinner = fighter1.Name;
          break;
        }

        fighter1.Health -= fighter2.DamagePerAttack;
        if (fighter2.Health >= fighter1.Health && fighter1.Health <= 0)
        {
          isWinner = fighter2.Name;
          break;
        }
      }
    }
    else
    {
      for (var i = fighter2.Health; i >= 0; i = fighter2.Health)
      {
        fighter1.Health -= fighter2.DamagePerAttack;
        if (fighter2.Health >= fighter1.Health && fighter1.Health <= 0)
        {
          isWinner = fighter2.Name;
          break;
        }

        fighter2.Health -= fighter1.DamagePerAttack;
        if (fighter1.Health >= fighter2.Health && fighter2.Health <= 0)
        {
          isWinner = fighter1.Name;
          break;
        }
      }
    }
    return isWinner;
  }
}
```
