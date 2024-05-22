# Combat
(Updated May 18, 2024)

Combat occurs when a Carrier arrives at a non-allied Star or when a Carrier intercepts a non-allied Carrier in hyperspace. The combat summary can be viewed in the event log.

![Summary of a combat in the event log](img/combat-summary.png)

When 2 opposing Carriers arrive at an unclaimed Star on the same tick, the Carrier that has the most ships (or if equal, traveled the least distance in the current tick) will arrive at the Star first and receive the Defender Bonus (if enabled).

Starting with the defender, each side takes it in turns to deal damage to the opposing side. Damage dealt per turn is equal to the effective weapons level, factoring in weapons technology and specialist abilities. When damage is dealt, it destroys ships on Carriers and ships on the Star. Damage is dealt roughly uniformly to all Carriers and the Star per turn.

If multiple opposing Players are in combat at the same time, they will be split into Attackers and Defenders. The Defenders include the player who owns the star and the defender’s allies; the Attackers are all other players. Combat is repeated until there is one player remaining.

When a Star is captured, **all** of its Economy is destroyed and the winner is awarded credits (default is `$10`) per point of Economy. Industry, Science, Warp Gates and Star Specialists are undamaged and are captured by the winning player.

Combat can also occur between two carriers. When two carriers from non-allied players intercept each other they will engage in carrier to carrier combat. In carrier to carrier combat there is no defender bonus and damage is dealt simultaneously (not in turns).

> Note: In carrier to carrier combat, if the either side has **less than or equal ships** than the opposing side’s weapons technology level then the carriers will fight with **level 1 weapons**. This prevents players from exploiting one-ship carriers to chip away at incoming enemy forces.

The combat calculator is a useful tool to predict the outcome of combat. Simply input the defender and attacker’s weapons level and number of ships and it will present the outcome.The combat calculator may not account for all specialist buff/debuffs or other incoming reinforcements. Players should verify weapon levels and ship counts which are expected to be in effect during the combat.


## Combat Weapons Technology

When specialists with Weapons buffs/debuffs participate in combat, the following rules apply:

`effective weapons level = weapons technology + max debuff + max buff + defender's bonus`

1. Defender bonus is added independently of buffs/debuffs.
2. Weapon deduction (i.e Infiltrator specialist) is applied to the opposing side independently of buffs/debuffs.
3. If multiple specialists with buffs/debuffs participate, then the **highest** buff and **lowest** debuff are used.


<details markdown="1" style="color:orange;background-color:#222222">
<summary><small><i>Click here for more details about combat effective weapons calculation</i></small></summary>

`effective weapons level = weapons technology level + max debuff + max buff + combined defender bonus + deduction by enemy + special buff`

* `weapons technology level` = largest technology level available to any of the players participating on the player’s side in a combat

* `max debuff` = lowest (worst) debuff from any of the specialist belonging to any of the players participating on player’s side; debuff is negative, so it lowers the effective weapons level of the player’s side; debuffs do not stack, only the lowest one is used
    * Both Star and Carrier specialist with weapon debuffs are included in this category

* `max buff` = highest (best) buff from any of the specialist belonging to any of the players participating on player’s side; buff is positive, so it increases the effective weapons level of the player’s side; buffs do not stack, only the highest one is used
    * Only Star specialist that provides weapon buff in this category is War Machine

* `combined defender bonus` = defender bonus + asteroid field bonus + orbital cannon bonus (this is applicable at a Star only)
    * Orbital Cannon falls under this category and would stack with any other weapon buff

* `deduction by enemy` = lowest (worst) deduction imposed by an enemy’s specialist available to any of the players on enemy’s side; deduction by enemy is negative, so it lowers the effective weapons level of the player’s side; deductions by enemy do not stack, only the lowest (largest negative) one is used

* `special buff` = additional buff provided only by War Hero specialist (see War Hero specialist description for more information)

If calculated effective weapons level < 1, then effective weapons level = 1

Notes:

1. Effective weapons level is calculated at the start of the combat and is in effect until combat resolves, even if a carrier weapons specialist runs out of ships mid-combat and is destroyed during the combat.

2. Ship placement does not affect the effective weapons level calculation, as long as the ships participate in the combat. Star defender bonuses and star specialists are in effect even if there are zero ships on the star (i.e., all ships are on carriers orbiting the star).

</details>


For example:

- Player's weapon technology level = 10
- Specialist A has Weapons +3
- Specialist B has Weapons +1
- Specialist C has Weapons -2
- `effective weapons level = 10 - 2 + 3 = 11 weapons` *(Specialist B is ignored)*

## Formal Alliance Combat Rules

When formal alliances option is enabled then there are a few conditions that need to be met in order for combat to take place:

1. When a carrier arrives at a star, if the player is allied with the defender then no combat occurs.
2. When a carrier arrives at a star, if the player is not allied with the defender then combat occurs. 
    * 2a. Carriers in orbit (or arriving on the same tick) who are allied to the defender will help the defender. If the player whose carrier is helping the defender is also allied with the attacker, their diplomatic status will not be affected.
    * 2b. If the attacker wins and captures the star, then combat will repeat until there are no non-allies to the defender.
3. When a carrier intercepts another carrier in space, then combat occurs between non-allies.
4. When a player changes their diplomatic status from allied to neutral or enemy, then combat occurs with combat outcome displayed on the next tick. If diplomatic status is restored back to allies within the same tick, no combat occurs.

> Note: More than 2 players can be in orbit at the star provided that they are allied with the defender. Combat will not occur if the guest players are enemies but are both allied to the defender.


## Weapon Buffs and Specialists Stacking Example

Scenario:

    • Player A: weapon technology level = 11
        ◦ Defending star:
            ▪ Trade Port: -3 weapon
    • Player B: weapon technology level = 10
        ◦ Attacking star with carriers:
            ▪ Lieutenant: +1 weapon
            ▪ Destroyer: +5 weapon
            ▪ Smuggler: -1 weapon
            ▪ Infiltrator -1 weapon from the opposing side

The combat weapons level resolves to this:

    • Player A - weapons technology level 11 :
        ◦ Defender bonus = +1
        ◦ Max buff = 0
        ◦ Max (worst) debuff = -3 (due to Trade Port)
        ◦ Additional debuff = -1 (due to enemy's Infiltrator)
        Total weapons = 8


    • Player B - weapons technology level 10 :
        ◦ Defender bonus = 0
        ◦ Max buff = +5 (due to Destroyer; Lieutenant is ignored)
        ◦ Max (worst) debuff = -1 (due to Smuggler)
        ◦ Additional debuff = 0
    Total weapons = 14


## Combat FAQ

Here are some commonly asked rule clarifications for carrier-to-star and carrier-to-carrier combat:

#### Carrier to Star Combat

- Combat occurs in turns, the defender going ﬁrst dealing damage equal to their effective weapons level each turn.
- Attackers are awarded credits (default $10) per point of Economy destroyed.
- If the star is captured and the star has a specialist, it will be captured by the attacker.
- If there are more than 2 players attacking and the defender is defeated then the player with a carrier with the highest ship count will capture the star.
- If there are 2 or more players attacking an unclaimed star on same tick then the player with a carrier with the highest ship count will capture the star.
- If the attackers defeat the defender and they are enemies, then combat will continue until only one player remains or all players who remain are allied with the defender.
- Ship distribution among the Carriers and the Star does not affect combat outcome, except carriers (with or without specialist) are destroyed once they run out of ships.

#### Carrier to Carrier Combat

- Players deal damage simultaneously, not in turns. This could lead to mutual deduction.
- Combat occurs between carriers traveling to and from the same star. 
- Carriers can attack from the front (head-to-head combat) and catch up from behind (i.e., faster carriers can catch up to slower carriers).
- Carrier to carrier combat occurs when carriers travel through the same wormhole in opposite directions on the same tick.
- Gifted carriers do not participate in carrier to carrier combat.
- All carriers travel independently. When carrier-to-carrier combat occurs with one or both opposing sides having two or more carriers that end up at the same point of interception, the rules of combat are relatively complicated and are presented below.

<details markdown="1" style="color:orange;background-color:#222222">
<summary><i><small>Click here for more details about C2C combat</small></i></summary><br>

Let's assume there are 2 stars, StarA and StarB.
Let carriers A, B, C, D, constructed in this order.

A, B are in the same position on StarA => StarB and owned by Player1.
C, D are in the same position on StarB => StarA and owned by Player2 (who is hostile with Player1).
The positions of A, B and C, D are below 0.2ly in distance, which will be crossed within a tick.

C2C combat is computed:

1. A list of carrier positions is constructed, collecting metadata about the carrier, the current position and the predicted position next tick. 
This list is ordered in what MongoDB calls "natural order", practically likely equivalent to insertion order/age.
2. A carrier graph is constructed, mapping (destination, source) to the carrier position objects traveling between source and destination. The graph looks like this:
(StarA, StarB) => [C, D]
(StarB, StarA) => [A, B]

3. The graph is traversed, in order of insertion of the key. This means that the paths are sorted ascending by the oldest (by natural order) carrier traveling on them.
For each carrier X traveling on that path (in natural order, starting with oldest), all other carriers are checked if they will collide head-on or be overtaken by X within the next tick.
Gift carriers and carriers with combat-avoiding specialists are filtered out.

4. Combat ensues if one of the carriers collected in 3 is not allied to X's owner.

In this example, it means that A will fight the group of C, D.

</details>

<span style="color:grey">

\
*While this guide provides the general overview of the basic combat rules, each combat is unique and could be impacted by many different factors, including monthly flux, specific game settings, etc. If in doubt, it is recommended to seek advice on Solaris Discord server.*
\
\
<a href="#top">Back to top</a>
