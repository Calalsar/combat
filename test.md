import random
enemy_types = ["Orc","Zombie","Ghost", "Dragon"]
enemy = random.choice(enemy_types)
print("You have encountered a rogue", enemy)
if enemy is "Orc":
    enemy_health = random.choice(range(50,100))
    enemy_attack = random.choice(range(20,30))
    enemy_speed = 1
if enemy is "Zombie":
    enemy_health = random.choice(range(20, 200))
    enemy_attack = random.choice(range(5, 20))
    enemy_speed = 0.5
if enemy is "Ghost":
    enemy_health = random.choice(range(20, 50))
    enemy_attack = random.choice(range(50, 100))
    enemy_speed = 3
if enemy is "Dragon":
    enemy_health = random.choice(range(1000,2000))
    enemy_attack = random.choice(range(200,500))
    enemy_speed=5
enemy_stats = enemy_health, enemy_attack, enemy_speed
your_health = 100
crit_chance = random.choice(range(0,100))
your_attack = random.choice(range(20,50))
print("The enemy's health is", enemy_health)
print("Your health is", your_health)
while enemy_health > 0 and your_health > 0:
    enemy_damage = random.choice(range(enemy_attack-10,enemy_attack+10))
    your_damage = input("What will you do?  A: Slash! B: Shoot! C: Fireball! D: Punch!")
    if your_damage is 'A':
        your_damage = random.choice(range(your_attack-10,your_attack+10))
        print("You used Slash!")
        print("You dealt", your_damage, "to the enemy!")
        enemy_health = enemy_health - your_damage
        print("The enemy's health is now", enemy_health)
        if enemy_health == 0 or enemy_health < 0:
                print("You've slayed the", enemy)
                break
        print("The", enemy, "attacked!")
        your_health = your_health - enemy_damage
        print("The", enemy, "dealed", enemy_damage, "to your health!")
        print("Your health is now", your_health,"!")
        if your_health == 0 or your_health < 0:
                print("The", enemy, "slayed you! You died!")
                break
    if your_damage is 'B':
        your_damage = random.choice(range(your_attack-5,your_attack+5))
        print("You used Shoot!")
        print("You dealt", your_damage, "to the enemy!")
        enemy_health = enemy_health - your_damage
        print("The enemy's health is now", enemy_health)
        if enemy_health == 0 or enemy_health < 0:
                print("You've slayed the", enemy)
                break
        print("The", enemy, "attacked!")
        your_health = your_health - enemy_damage
        print("The", enemy, "dealed", enemy_damage, "to your health!")
        print("Your health is now", your_health,"!")
        if your_health == 0 or your_health < 0:
                print("The", enemy, "slayed you! You died!")
                break
    if your_damage is 'C':
        your_damage = random.choice(range(your_attack-20,your_attack+20))
        print("You used Fireball!")
        print("You dealt", your_damage, "to the enemy!")
        enemy_health = enemy_health - your_damage
        print("The enemy's health is now", enemy_health)
        print("The", enemy, "attacked!")
        your_health = your_health - enemy_damage
        print("The", enemy, "dealed", enemy_damage, "to your health!")
        print("Your health is now", your_health,"!")
        if your_health == 0 or your_health < 0:
                print("The", enemy, "slayed you! You died!")
                break
    if your_damage is 'D':
        your_damage = random.choice(range(your_attack-1,your_attack+1))
        print("You used Punch!")
        print("You dealt", your_damage, "to the enemy!")
        enemy_health = enemy_health - your_damage
        print("The enemy's health is now", enemy_health)
        if enemy_health == 0 or enemy_health < 0:
                print("You've slayed the", enemy)
                break
        print("The", enemy, "attacked!")
        your_health = your_health - enemy_damage
        print("The", enemy, "dealed", enemy_damage, "to your health!")
        print("Your health is now", your_health,"!")
        if your_health == 0 or your_health < 0:
                print("The", enemy, "slayed you! You died!")
                break
    if enemy_health == 0 or enemy_health < 0:
        print("You've slayed the", enemy)
        break
    if your_health == 0 or your_health < 0:
        print("The", enemy, "slayed you! You died!")
        break
potions = 5
potion_use = input("Will you use a health potion? A: Yes B: No")
if potion_use is 'A':
    your_health = your_health + 50
    potions= potions - 1
    print("You have", your_health, "health!")
