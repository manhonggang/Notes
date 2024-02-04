> Welcome to the first deep-dive entry in our ongoing League of Legends design values_! A few weeks ago we spoke about our core design pillars in League, and we promised additional entries that would go in-depth with each particular one.
> 
> Up today we’ve got **Richard ‘Nome’ Liu**, an environment and clarity designer for League of Legends. In addition to talking at length about gameplay clarity, Nome’s also going to be talking about the decision-making that went into the development of **jungle timers**. So read on to hear Nome’s thoughts on clarity and why it’s so important to League of Legends as a whole!
> 
> _

 ![](http://web.archive.org/web/20141007114912im_/http://forums.na.leagueoflegends.com/board/image.php?u=283&dateline=1387558682) Chris ‘Pwyff’ Tom

## What is Clarity?

![](http://web.archive.org/web/20141007114912im_/http://forums.na.leagueoflegends.com/board/image.php?u=2929600&dateline=1337379674)This article is written by clarity and environment designer Richard "Nome" Liu

Can you spot exactly where you are in a teamfight?

When you glance at the scoreboard, can you figure out whether you or your opponent has a higher minion score in less than three seconds?

On first use - without reading the tooltip - can you understand the full effects of an ability?

On a deeper level, how much information does a player need to make a meaningful choice, and how many more layers can be added before that choice turns into bookkeeping of obscure information?

[![](http://web.archive.org/web/20141007114912im_/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/sc_thumb.png)](http://web.archive.org/web/20141007114912/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/sc.png)

Where information is presented is important. When Shyvana was updated, her melee attack effects were moved to their affected ability tooltips -- since that's where they're most relevant!

These are the kind of challenges – and more – that the **gameplay clarity** team tackles on a daily basis, and they're ones that we firmly believe can be improved in League of Legends. As mentioned in our design values dev blog, gameplay clarity is incredibly important for the evolution of League of Legends and our mission is to ensure that players are fighting their opponents, _not_ the game.

But what is gameplay clarity? Clarity is pervasive. It's in visuals, gameplay, design, art, and everything in-between. In League of Legends, gameplay clarity relates to the availability of information as well as the intentional obfuscation of it. We can make clear gains – like updating minion particles to be more accurate in their direction – but these aren’t what we’re here to discuss.

So what _are_ we here for? Well, with the push of **Jungle Timers** to the PBE, we felt this would be a good time to discuss gameplay clarity in spaces yet to be explored as well as how we're aiming to improve your gameplay experience.

## Jungle Timers: Putting the Focus on Mastery

Boiling down what we talked about in our design values, League of Legends provides three basic paths to mastery: personal expertise, teamwork, and adaptability – our focus will be on the first. Personal expertise is a complex soup of skills but we can generally agree that elements like mechanical mastery, situational awareness, and game knowledge are vital ingredients.

Most of these are universal to the League of Legends experience and are agnostic to the map, mode, or champion you play – though a few of them can be overloaded based on your preferences. Regardless, we’ve also declared that a few things _aren’t_ part of the experience, like hardcore multi-unit micromanagement, rote memorization of patterns, or bookkeeping.

[![](http://web.archive.org/web/20141007114912im_/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/tm_thumb.png)](http://web.archive.org/web/20141007114912/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/tm.png)

The new jungle timers are nestled at the top of the screen. They won't be presenting any new or hidden information. Rather, they present existing information in a visual display.

Jungle timers fall into that last case, and serve as an example of important information being presented in an impractical manner. Looking back, there was a lot of internal debate over whether this level of information should be exposed.

On one side, a case could be made that map-level objective awareness is a significant aspect of skill – and to that, we wholeheartedly agree. We would not, for example, alert you when an opponent entered your immediate radius from fog, nor would we ever track enemy cooldowns for you. Your interactions with your opponents are sacred and we will always leave those interactions alone.

On the other side – and here's what finally changed our minds – the jungle is a constant environment; unlike champions, monsters will always be where you expect them to be; unlike cooldowns, there is no variability in respawn rates. With timestamps available in the team chat window, timing of jungle monsters often came down to whoever remembered to type it out. We also don’t want to beat around the bush here: the emergence of third party applications put fuel on the fire, but they only increased our confidence that such a feature was in line with our values.

Ultimately, the question we asked was whether bookkeeping of jungle timers (which, as I mentioned before, was often solved by doing quick math in the chat box) contributed _satisfaction_ of the play experience and we realized it was just too much of a routine task to be of significant value.

## Turrets: How Clarity is Applied

But this dev blog isn't all about jungle timers (although they're the most contextually relevant), and I'd like to highlight other uses of clarity. We're not always about displaying _all_ information – clarity is about intentionality: a game that makes every piece of knowledge available creates information paralysis, while a game that hides all information promotes mental archiving rather than rewarding moment-to-moment mastery. The job of design is to use informational clarity (or the lack thereof) to create interesting situations.

[![](http://web.archive.org/web/20141007114912im_/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/tc_thumb.png)](http://web.archive.org/web/20141007114912/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/tc.png)

It's extremely important for players to understand when they're being targeted by a turret. At the same time, it's important to leave space where players can be baited into taking turret shots as well.

To provide an example in which clarity is important in limited scope, we can look at turrets. It’s incredibly important to understand when you’re targeted by a turret, as their attacks are especially impactful and feature a unique set of rules: they ignore a portion of your armor and deal increased damage with each successive hit. To this end, turrets utilize exaggerated ceremony: there’s a persistent targeting laser, a distinct sound alerts you when you’re targeted, and it fires bright balls of energy. Now here’s something turrets _don’t_ feature: a persistent range indicator (outside of Co-Op vs AI and beginner games).

Certainly a range indicator would improve clarity around the turret – no one denies this. A scenario where one player harasses another under the turret is rife for plays to be made, and this contributes heavily to our decision-making. When an indicator is present, the play is between the aggressor and the indicator rather than the aggressor and the defender. If we were to make turret range indicators permanent, then aggression would be boiled down to who can toe the line better, which ultimately decreases the potential for interesting plays to arise.

## The Sanctity of Clarity

For my final point, we’ve covered when information should be exposed and when it should be hidden. Now, I want to briefly touch on when information is available but inaccessible.

A good example here would be the visual update to Karthus’ Lay Waste. The previous particle grossly misrepresented the ability’s area of effect, while the new particle is far more functionally accurate. In approaching a change like this, the argument could be made that inaccurate particles create gameplay _through_ deception, but this collides directly with clarity as a core value: the _game_ should never deceive players. The player should deceive other players!

[![](http://web.archive.org/web/20141007114912im_/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/kc_thumb.png)](http://web.archive.org/web/20141007114912/http://riot-web-static.s3.amazonaws.com/images/news/June_2014/DDBC/kc.png)

It was easy to hide the old particle, but the resulting gameplay was deceptive. The new particle communicates the gameplay clearly.

On this point, creating gameplay through intentional miscommunication doesn’t actually add depth or personal mastery. One Karthus may be strategically and tactically superior to the other, but if the better Karthus loses because he didn’t know the skittle extended _beyond_ its indicated hitbox, that’s not a victory that can be chalked up to skill. The job of clarity is to refine knowledge such that both parties can make intelligent choices. If one player makes a fatal error (either due to a lack of knowledge or mechanical skill), they should lose due to their opponent's superior skill, not the inconsistency of a game rule (that all particles accurately represent their hitboxes).

## Onwards!

We’re passionate about pushing League of Legends to be more readable, understandable, and usable – all so that we can put the focus back on personal mastery. On that note, while clarity is a design value we've been pursuing for some time, it's also one where we have great opportunities to grow. Our hope is that as we continue to add more clarity to League of Legends, we'll also be pushing the envelope of player skill.

Either way, we absolutely welcome your feedback on all of these points – and call us out when we fall flat! If you have any questions, comments, or suggestions on how we can improve the game from a clarity standpoint, be sure to leave them in the comments.