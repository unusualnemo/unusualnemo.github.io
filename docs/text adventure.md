*link to text adventure repo*

---

```python
import random
import sys

# CLASSES ==============================================

class Player:
    def __init__(self, name, damage, speed, health):
        self.name = name
        self.damage = damage
        self.speed = speed
        self.health = health

    def __repr__(self):
        description = """Okay, so your name is {name}.
        After a bit of math, your stats are as follows:
        Damage: {damage}
        Speed: {speed}
        Health: {health}""".format(name = self.name, damage = self.damage, speed = self.speed, health = self.health)
        return description

    def die(self):
        print("")
        print("YOU DIED")
        sys.exit()

    def attack(self, monster):
        monster.health -= self.damage
        print("You have attacked the creature for {damage} hit points. It now has {health} hit points.".format(damage = self.damage, health = monster.health))
        if monster.health <= 0:
            monster.die()

class Monster:
    def __init__(self, damage, speed, health):
        self.damage = damage
        self.speed = speed
        self.health = health

    def __repr__(self):
        description = ""
        return description

    def die(self):
        print("The creature has died!")

    def attack(self, player):
        player.health -= self.damage
        print("You have sustained {damage} damage. Your health is now {health}.".format(damage = self.damage, health = player.health))
        if player.health <= 0:
            player.die()

# FUNCTIONS ============================================

def dice_roll(sides):
    result = random.randint(1, sides)
    return result

def fight(player, monster):
    print("A monster leaps out at you!")
    while monster.health > 0 and player.health > 0:
        print("")
        if player.speed < monster.speed:
            print("The monster strikes first this turn!")
            monster.attack(player)
            if player.health > 0:
                print("You retaliate!")
                player.attack(monster)
        else:
            print("You get the jump on the monster this turn!")
            player.attack(monster)
            if monster.health > 0:
                print("The monster fights back!")
                monster.attack(player)

# NAME PICKER ==========================================

print("")
player_name = input("""You stand at the mouth of a deep, dark cave on the side of a tall, dark mountain.
Your name is ...
""")
print("")

# STATS PICKER =========================================

player_strength = input("""Ah! So your name is """ + player_name + """.
Well, it must have been a difficult climb to get here.
How strong are you from 1 to 10?
""")
player_strength = int(player_strength)

if player_strength < 1:
    player_strength = 1
    print("""Surely you aren't THAT weak!
I'll put you down as a 1.""")
if player_strength > 10:
    player_strength = 10
    print("""Okay, okay. You think you're so strong...
I'll put you down as a 10.""")
print("")

if player_strength >= 8:
    player_constitution = input("""So you're pretty beefy, huh? Well, are you as durable as you are strong?
How tough are you from 1 to 10?
""")
elif player_strength <= 5:
    player_constitution = input("""Pretty pathetic then? Well, can you at least take a punch?
How tough are you from 1 to 10?
""")
else:
    player_constitution = input("""Not very weak... but also not very strong... Well, can you at least take a punch?
How tough are you from 1 to 10?
""")
player_constitution = int(player_constitution)

if player_constitution < 1:
    player_constitution = 1
    print("""You couldn't possibly be THAT frail!
I'll put you down as a 1.""")
if player_constitution > 10:
    player_constitution = 10
    print("""Hahaha! You think you're so tough...
I'll put you down as a 10.""")
print("")

if player_strength >= 8:
    if player_constitution >= 8:
        player_dexterity = input("""Well, well, well. You're pretty strong AND tough. But with all that extra muscle are you nimble?
How quick are you from 1 to 10?
""")
    elif player_constitution <= 5:
        player_dexterity = input("""So you can deal damage, but you can't take it? Well, maybe you can dodge it?
How quick are you from 1 to 10?
""")
    else:
        player_dexterity = input("""So you're strong, but a little less durable. Well, maybe you make up for it with speed?
How quick are you from 1 to 10?
""")
elif player_strength <= 5:
    if player_constitution >= 8:
        player_dexterity = input("""So you can't deal a lot of damage, but at least you can take quite a few punches. For the sake of your inevitable brain damage, I hope you can dodge some of those punches.
How quick are you from 1 to 10?
""")
    elif player_constitution <= 5:
        player_dexterity = input("""Uhm, are you sure you want to be here? You don't seem well equipped to go into spooky caves to fight monsters... You better be really good at dodging.
How quick are you from 1 to 10?
""")
    else:
        player_dexterity = input("""Well, at least you're more durable than you are strong. But I hope for your sake that you can run from a fight.
How quick are you from 1 to 10?
""")
else:
    if player_constitution >= 8:
        player_dexterity = input("""Oh? So you're a bit better at taking punches than dealing them? Can you at least dodge some of them?
How quick are you from 1 to 10?
""")
    elif player_constitution <= 5:
        player_dexterity = input("""Wow, that weak, huh? Well, hopefully you can run away from a fight!
How quick are you from 1 to 10?
""")
    else:
        player_dexterity = input("""So, pretty average, huh? Well, maybe you're better at running away?
How quick are you from 1 to 10?
""")
player_dexterity = int(player_dexterity)

if player_dexterity < 1:
    player_dexterity = 1
    print("""You couldn't be THAT slow if you tried!
I'll put you down as a 1.""")
if player_dexterity > 10:
    player_dexterity = 10
    print("""You're a bit cocky, huh?
I'll put you down as a 10.""")
print("")

#math out stats

player_damage = round(player_strength * )
player_health = player_constitution * 3

# CREATE PLAYER OBJECT =================================

player_character = Player(player_name, player_damage, player_dexterity, player_health)
monster1 = Monster(5, 8, 10)
monster2 = Monster(8, 13, 15)

# SETTING ==============================================

print(player_character)
keep_going = input("press enter")
print("")
print("""You stand at the mouth of the cave, clutching your old, worn shortsword.
You've come here seeking treasure.
You've been warned about monsters,
but you're prepared to fight.
""")
keep_going = input("press enter")
print("")
print("--------------------------")
print("")

# FIRST FIGHT ==========================================

fight(player_character, monster1)
keep_going = input("press enter")
print("")
print("--------------------------")
print("")

# HEALING ==============================================

healing = round(player_health * )
player_character.health += healing

print("""You enter a separate chamber and find a luminescent pool.
You drink from the pool and gain {healing} hit points.
You now have {health} hit points.""".format(healing = healing, health = player_character.health))
keep_going = input("press enter")
print("")
print("--------------------------")
print("")

# SECOND FIGHT =========================================

fight(player_character, monster2)
keep_going = input("press enter")
print("")
print("--------------------------")
print("")

# TREASURE =============================================

print("""You enter a spacious chamber,
glimmering with precious stones.

You have found the treasure!

Thank you for playing!!
""")
```
