Difficulty:IntermediateLength:ShortLanguages:

Melee fighting is a favorite pastime in videogameland, the core of countless series both well-known and obscure, and a tense and gripping experience when done right. Many a game developer has taken a game of two beings biffing it out until one can biff no more and thought, "this would be so much better if there were _tons_ of baddies!" Sometimes this is true, but often the sum is greater than its parts, and fighting lots of "baddies" at once isn't as exciting, deep, or nuanced as fighting one at a time.

Many melee combat games don't use any particularly special AI when fighting multiple opponents. This often means that fighting two opponents is exponentially harder than fighting one, because they'll both attack at the same time but you can only really retaliate against one of them. In the worst cases, when fighting hordes of enemies, this can mean that the optimal strategy is to lead the enemy into a single-file line, then attack them one at a time while backpedaling! That doesn't feel very fantastic or exciting, does it?

<iframe width="600" height="338" data-src="//www.youtube.com/embed/ukXrOSFH-_Y" frameborder="0" allowfullscreen="" src="//www.youtube.com/embed/ukXrOSFH-_Y"></iframe>  

Skip to 0:53.

Enter the "battle circle". This is a piece of AI code that tells enemies to intentionally encircle themselves around the player and only attack when the player has a chance to react. This forces enemies to fight in a style and tempo that's a lot more fun for the player... even if it's actually a really bad fighting tactic!

The main reason you'd want to use battle circles is to let the player _feel_ like they're fighting many enemies at once, without actually facing the _real_ challenge of fighting many enemies at once. Thus, at its very core, a battle circle is an illusion. You're intentionally making things easier for the player so they can experience the _fantasy_ of taking on a bunch of dudes at once and knowing you're going to come out alive, just like in any martial arts movie.

<iframe data-src="//www.youtube.com/embed/PDQPIJSO0XA" height="338" width="600" allowfullscreen="" frameborder="0" src="//www.youtube.com/embed/PDQPIJSO0XA"></iframe>  

Skip to 1:13.

A battle circle doesn't have to work the same way for every game; if you choose to use one you must spend time tailoring it to your game. On one end of the spectrum, you have "cinematic" battle circles, like in Assassin's Creed or Batman: Arkham Asylum, where enemies patiently wait their turn before attempting to attack, and give the player plenty of warning to deal with incoming attacks. On the other end, you have "dangerous" battle circles, like in Dark Souls, where enemies will try to stay out of each other's way, but otherwise have no problem mobbing you en masse.

I use the words "cinematic" and "dangerous" to describe the sort of experience the player is expected to have when inside the circle; is it more of an exciting audiovisual experience that the player should feel _comfortable_ in, or should it be a _vulnerable_ position the player should try to avoid?

<iframe data-src="//www.youtube.com/embed/hnj4RHFG038" height="338" width="600" allowfullscreen="" frameborder="0" src="//www.youtube.com/embed/hnj4RHFG038"></iframe>

This concept can be simplified further as simply managing the amount of _pressure_ on the player. Specifically, this is the amount of motivation the player has to react to the enemies in the battle circle. A low-pressure circle will let the player wait for incoming attacks to counter, or proceed to attack a particular enemy without immediate retribution. A high-pressure circle will force the player to pick "fight or flight" as soon as they are in the circle, so that entering the circle in the first place should be a premeditated tactical decision. While inside such a dangerous circle, the player must immediately decide who to attack, who to counter, and when and how to escape.

I've provided a fully-functional, if minimalistic arena-style beat-em-up in [the example Unity files](https://github.com/tutsplus/battle-circle-ai). If you don't use Unity, you should still have a rough idea of how to adapt the battle circle code to whatever language and engine you're using. The files you'll be interested in are [EnemyMob.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/EnemyMob.cs?source=cc) and [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc).

Here's the battle circle in action. Click the demo to give it focus, then use the arrow keys to move and press **X** to biff.

How it Works
------------

The battle circle AI basically works like this (from an enemy's perspective):

First, walk towards the player until I get within a "danger" radius

![gamedevtuts_battlecircle_600_01](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_01.png)

While in "danger" mode, don't get too close to another enemy, unless I am given permission to attack the player. (See [Avoider.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/Avoider.cs?source=cc).)

![gamedevtuts_battlecircle_600_02](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_02.png)

Also while in "danger" mode, try to approach the player. If there are too many enemies in my way, I will effectively not be able to reach the player until the enemies move or the player moves.

When the player is in my "attack" radius (roughly the maximum range of my attack) ask the player if I'm allowed to attack. If so, add me to the list of current attackers on the player object. (See [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc).)

![gamedevtuts_battlecircle_600_03](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_03.png)

*   If there are already the maximum allowed number of attackers on the list, I'm denied permission.
*   If I'm denied permission, try strafing for a second or two in a random direction until I'm given permission.
*   If the player moves out of attack range—even if I'm attacking—remove me from the attacker list.
*   If I die, or am stunned or otherwise unable to attack, remove me from the attacker list.

The _maximum allowed number of simultaneous attackers_ (`simultaneousAttackers` in [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc)) is critical in balancing your battle circle. A higher number causes an exponential increase in _pressure_. In the example demo I have it set at `2`; less twitchy and more "cinematic" games set it at `1`. If you put this number too high, you defeat the purpose of the circle, because large groups of enemies become unassailable or can only be defeated with uninteresting poke-and-run tactics.

Of similar importance is the _enemy attack rate_ (`attackRate` in [EnemyMob.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/EnemyMob.cs?source=cc)). This is not the fastest possible attack rate of the enemy, but how often they will _choose_ to attack when given permission. As you would expect, a lower number increases _pressure_, but you should generally have this be several times higher than the real attack rate. You can make this rate a bit more unpredictable (and thus the amount of _pressure_ slightly less predictable) by increasing `attackRateFluctuation`, which will increase or decrease the attack rate after each attack.

Using this system, you have the basic means to create that illusion of power that makes it a lot more fun for your players to fight lots of enemies at once.

Conclusion
----------

There are tons of minor changes and additions you can make for combat inside the circle to be even more interesting:

*   A "stun" or "counter" attack the player can use to put enemies out of combat for a few moments, so the player can attack other enemies in the circle
*   A "dodge" move for the player to quickly travel into, out of, or within the circle
*   "Push" and "pull" moves that let the player move enemies into and out of the circle
*   Ranged enemies that will snipe at the player through openings in the circle, and encourage the player to force themselves through the circle to attack these enemies first
*   Special "captain" enemies that increase the attack rate of enemies near them, or ignore permission to attack, and thus increase the _pressure_ of certain portions of the circle

So get those creative juices flowing! This is just the beginning: make the battle circle a core part of your gameplay, and make your own version of the circle that fits well with _your_ game.