---
title: Narrative Legos with Ken Levine - GDC 2014
source: https://www.youtube.com/watch?v=58FWUkA8y2Q
author:
  - "[[GameSpot]]"
published: 2014-03-25
created: 2026-08-06
description: It's clear that narrative is an important part of video games and something that the audience deeply relates to. However, the strengths of interactive media are player participation, the ability to ex
tags:
  - clippings
modified: 2026-08-06T21:33:26+08:00
---
![](https://www.youtube.com/watch?v=58FWUkA8y2Q)

> 中文翻译整理：[[叙事乐高 - Ken Levine GDC 2014 演讲整理]]

It's clear that narrative is an important part of video games and something that the audience deeply relates to. However, the strengths of interactive media are player participation, the ability to experience content in different ways on different playthroughs and the fact that the content is not static. It's time for narrative to deeply embrace these elements.  
  
Follow BioShock: Infinite at GameSpot.com!  
http://www.gamespot.com/bioshock-infinite/  
Official Site - http://www.bioshockinfinite.com/  
  
Check out our review!  
Watch - http://www.youtube.com/watch?v=jSA9AsdBh00  
Read - http://www.gamespot.com/bioshock-infinite/reviews/bioshock-infinite-review-6405762/  
  
Visit all of our channels:  
Features & Reviews - http://www.youtube.com/user/gamespot  
Gameplay & Guides - http://www.youtube.com/user/gamespotgameplay  
Trailers - http://www.youtube.com/user/gamespottrailers  
MLG, NASL & eSports - http://www.youtube.com/user/gamespotesports  
Mobile Gaming - http://www.youtube.com/user/gamespotmobile  
  
Like - http://www.facebook.com/GameSpot  
Follow - http://www.twitter.com/GameSpot  
Stream Live - http://twitch.tv/GameSpot  
  
http://www.gamespot.com

## Transcript

**0:01** · um I've always been a fan of systemic games I mean I grew up really I've been playing civilization since the first one that came out and I'll play every version of every civilization every add-on pack forever XCOM is another one of my favorite games I grew up playing Paper you know hex based board games but my games that I've worked on haven't really been like that with the exception of Freedom Force a little bit um but

**0:23** · narrative and and systemic uh they kind of fight with each other and so we haven't really been able to sort of make you know really integrate system work as much as possible um so to do something really different we really had to go back to the drawing board and that required a a new structure um a smaller

**0:43** · group of people and time that was the most important thing time to fail time to fail for a long period where you don't have 150 people who are looking you and saying dude you know what am I supposed to be doing today um I want to say a couple things that this is not this talk is not a design for a specific game I'm not here to pitch a product it's a GDC talk this you're all developer is I'm a developer um this is just early early thoughts on something

**1:11** · that I want to put out there um this is not like a specific development plan we're oh my God they cut that feature there's no features here yet that we're just really talking on a very high level uh it's not intellectual property you're going to see nothing here like a Rapture Colombia you're going to see me stealing a lot of meta intellectual property from

**1:30** · other people that we're just using for the purpose of example um and if you're headline if you're a journalist and your headline says LaVine reveals new game you've written the wrong \[ \_\_ \] headline but one of you will write it I guarantee it

**1:45** · um all the content here you're going to see is basically just stolen from other places and from from other great games but it's um the content the the the kind of Worlds the kind of characters it's just for it's just for the purposes of example so but what that's a lot of what this isn't what this is It's a conversation it's my way of contributing to a conversation which I think is already going on a lot of people I respect um in the industry have been thinking about some of these things and I'm this is me and my team trying to bring our sort of approach to it

### What this is

**2:19** · um and that's my PowerPoint skills at work um so it's our initial scratching in there to try to figure out a way to really make player driven these are the keywords player driven replayable

**2:36** · narrative okay so I want to say one thing you a lot of times these talks are like well don't record this don't do it don't take pictures don't do anything like that this is completely open source take pictures film it put it on the internet whatever you want to do you know do a rift tracks to it I don't care um and but you know tweet it and most importantly if it's something useful to you steal whatever you want from it um I

### Open Source Talk

**3:00** · don't know how much it's going to be useful because it's pretty early but there's nothing proprietary here that you should be remotely nervous about leveraging for your own stuff all right so we talked some about the the negatives of linear narrative the ex it's incredibly expensive to make

### Negatives of Linear Narrativa

**3:17** · the individual pieces don't speak to each other they do emotionally like what happened to Booker at the beginning of infinite talk to what happened at the end in the player's mind but the game there's nothing in the game in the way in Civilization your choices you make beginning really make make an effect at the end like in a meaningful meaningful way you know which which you know types of cities you built which types of um of cultural trees you've taken um they don't really do that in linear narrative um branching does exist in a lot of games not so much in our games but there's still X number of states and

**3:49** · what I'm going to talk today is not X number of states but x to the Y number of states I haven't taken math since 1983 so I think that's right um it also linear narrative doesn't really fully embrace the P Unique power of games which is replayable and player

**4:09** · driven you know as much as I love the narratives we did really we we were so much feeling you know we knew the constraints of it so much that we kind of made a lot of meta commentary on constraints because we we it is a constraint and though I I love that form I think we sort of said what we had to say and we want to see what's past it and most importantly it's not player driven you are seeing the same story your friend is seeing or you're seeing X of Y versions of a story your friend is

**4:36** · seeing um multiple endings still mean a fixed number of player States there's five endings there's not x to the Y endings um and one of the most frustrating parts for me is you can only add in a narrative game traditionally sorry add onto a narrative game meaning here's another chunk which you play that it's subsequent to what you already played where games like Civilization games like XCOM you can add into the

**5:03** · experience and enhance the The Experience from the very beginning of the game so that's going to be a focus of what we talk about today as well um I don't want to underplay the work that's being done in this area I think you know if you look at stuff at BioWare the stuff at you know The Witcher guys are doing there's a lot of really great work about opening up narrative but I think they're they're taking a fundamentally different approach but I don't in no way do I want to say their work is an extraordinary and important um so how do we traditionally

### The Traditional Approach to

**5:34** · think about AI whenever I talk to people about AI a lot of people say to me when do you think an AI is going to be like a person when is it going to pass the Terin test and I think that's fundamentally too ambitious a way to think about characters and AIS um because I think we've all demonstrated there's nobody on the planet who's even close to this I think we're several Paradigm shifts of not just technology

**5:56** · as a writer it's hard enough to write one good character let alone um a character that can react to any arbitrary thing and say clever and funny lines while he does it so a really robust solution to this lies Beyond any technology or creative Horizon that we currently have so we're really scratching at the surface but I think we're giving up the um the good for the great because I think there's real major steps we can make here but we have to refocus our attention a little bit um if

**6:25** · you're over ambitious can lead to paralysis and I think that's what happens well we can't do it so let's just not even really try um so let's try um some First Steps physics remember when physics remember 20 years ago there was no physics in games physics was an animation that played when you drop something that had no did not speak to any math really of any kind um but when

### Physics Wasn't Built in a Day

**6:51** · they started with physics and I got very excited because I love simulation they started very simply with you know 2D circles and rectang angles and spheres and and cylinders and access align boxes and you know so on and so on and so on now there's cloth and liquid but they're still dealing with uh a subset and they

**7:12** · keep building up from that subset but every time they add something to that subset it gets more powerful and it gets more real feeling but remember back in the day when the first things appeared it was you weren't like well \[ \_\_ \] this it's not perfect physics let's forget it I'm not going to play it it was exciting and I think that there's there's a path to take here with characters so if we don't try to model everything but Model A Li a set of limited and believable and

**7:36** · impactful things so let's try as we think about this to set some goals create a narratively driven experience where the narrative elements are nonlinear and they talk to each other they interact with each other they they they bounce off one another like um I was about to make some science reference and again I was a drama major so I completely and what that reference would be like electrons or atoms does that sound right okay um um and all

**8:06** · these narrative elements trigger off of player action not off aoral action meaning not like we decide like in an infinite for instance um you enter a bounding box generally narrative thing what happen when you enter a bounding box and we say oh you enter the bounding box and conditions X Y and Z or met so will trigger this narrative event but those are generally off of where the auth author intends them to happen not where the player um arranges for them to happen these triggers these things that

**8:35** · change the narrative State the things you can interact with in the Nar have to be transparent to the player so you're not just like out there doing things and people are reacting in completely crazy ways we want to show you the the things the the the passions and I'll talk to you about what passions are in a minute what they are and how you can interact with them so let's um I hope Todd Howard isn't here um but let's just

**8:59** · sort of take his you know their design and it's you know a lot of MMO style design and single player MMO like Skyrim design um Basics so we have a game we can talk about that isn't necessarily in any way shape or form the game we're making but it gives you some basis of understanding to apply the new stuff too so let's assume a game kind of open worldy with factions you can choose between with quests and character growth and you know armor to collect and and monsters to fight and crafting of all

**9:28** · kinds um I would expand the crafting in in um I take a page out of dark Cloud's book for this example too Dark Cloud 2 hope you've all played it it's like one of the best games ever um you can actually craft there you go you can actually Craft um actual towns and buildings and those there's a cycle you go to the dungeon you collect loot you collect crafting materials you come back to the town you can build parts of the town that gives you Buffs that gives you new characters that gives you new opportunities there's a great cycle what I talk about here is the strong Loop between non-combat and combat a really strong non-combat combat Loop nonlinear

**10:00** · Quest structure is also critical here all right so here's my incredibly Innovative World um for villages imagine an open worldy kind of thing there an arc Village there's a dwarf Village there's a goblin Village and a elf Village and then there's you you come into the world and so now we start getting into the stuff that is um the stuff we've been thinking about and the stuff we we've been focusing our brain on so in the orc Village there's lots of

**10:32** · people there's five stars in each town now that number is is placeholder but what I want is when I say a star these are the characters that really matter and the question is I don't want to overwhelm the player with a thousand characters that matter because you'll just you just won't be able to track them so the number is really how many people can the can the player really track how many stars can a player track okay what is a star a star is an NPC

### What's a Star?

**11:00** · with a set of capital P passions a defined term which I'll Define in a minute um what's passion okay these are not full psychological models you know as I I said Tech before has been trying to really fully simulate a human being and all you know and how they work but I'm not really trying to do that let's go to literature and media so you know a bunch of stuff about Luke Skywalker he has passions right what are Luke's passions he wants to prove himself he wants to go on adventures he has issues with his dad um these are things that

### Passions Are Not Full Psychological Ma

**11:32** · really Define him there's things that probably exists we all have things that exist and think about just for about Luke just forg out the people you know people you work with you know a bunch about their passions but like you don't really know about their kinky weird \[ \_\_ \] that goes on at home and maybe you don't even want to know um so there are things

**11:49** · that don't really matter you know maybe Luke is a vegetarian maybe he's one of those really jerky vegetarians who won't stop I'm a vegetarian so I kind of know um he's got Pro know he's got a terrible tooth decay problem he's got OCD and like these are things that exist in Luke Skywalker but they're just not relevant to to the experience at hand so let's not worry about that stuff let's just worry about his passions so a passion is what a star cares about relative to the act of the player meaning relative to the things the player can impact

### A PASSION is what a STAR cares about relative to the actions of the PLAYER

**12:20** · upon a passion is transparent to the player meaning that the player can see these passions and see how they are the character the APC is feeling about them in relation to these passions a passion must be responsive to players actions it

**12:37** · has no meaning if you can't do anything about it that's what you know you're you're the star you're you're the center of this game you want to be able to impact these passions so let's meet Frank one of the stars of the YC Village he's a blacksmith he has a store hey guess what he sells a lot of armor and weapons and crap like that but unlike most blacksmiths who just stand there and deal with you on price um Frank is a little more complicated he's he's kind of a deep guy um he's got

### Anatomy of a Passion

**13:04** · three passions let's just talk about one of those passions he has a passion which is he hates elves and a lot of Orcs share this passion um and can you see the cursor I'm drawing with here yeah there it is um oh great it's

**13:20** · completely offset from my screen um so um so you see the every all the characters passions or feelings value in regard to this thing so Frank here is about hating elves but this is really about how does he feel about you in relation to hating elves well he doesn't know you at first so he's like he's he's neutral with you um you know he's right in the middle but as you do things relative to elves either doing bad crap to elves or doing good stuff to elves he likes you more or less in regard to this passion okay um so example Frank hates

**13:53** · elves you kill an elf woo he likes you for that and his passion in this regard will go move towards the positive um nice and simple on the other side he hates elves you help an elf of any kind you know you do a quest for an elf you rescue an elf you build a house for an elf you woo an elf he's going to feel more negative about this that's this is all pretty simple and you've seen some stuff like this in games before already um so he but he Frank has three passions that you know about the beginning and let's say the passions are he hates elves he wants a temple to the old gods

**14:23** · built not the new Gods the old gods and he wants to woo Barbara the orc because she beautiful um and you can impact all these passions you can help him build the temple you can help him prove himself to Barber all you know these are all normal sort of questing things and Building Things and crafting things and fighting things and Dungey things and collecting things but they're all imp impacted by you these won't move on their own except what you do um relative to them now the macro passion okay this

**14:56** · is where it gets interesting to me the macro p passion macro passion and this is where my math won't come in again I'm going to say it's a function I'm going to say it's an average and I'm probably completely wrong because there's probably somebody telling me I can't be an average but I'm saying it's an average so shut up um it's it's a function or an average of the three of the three um micro passions yield a a

**15:17** · basically their overall feeling about you and remember so it's not just one feeling it moves on on all these different axes those yield a larger feeling about you and you see these little black lines um on these on the on the on the macro passion that's that gold bar those are called thresholds and when that when when you pass certain thresholds on that Frank will start doing stuff for you or doing stuff against you depending on how you're deal dealing with Frank so for

**15:45** · instance you um steal the El king's crown remember he does not like elves so that micro passion feeds into the macro passion and ding oh I missed a slide um you kill some Elves at the beginning um ding Frank says oh guess what there's a 20% discount in my store from now on as long as you don't go back past that threshold because you do things he doesn't like then you do something bigger you you steal an elf king's crown ding Frank offers to send NPC's henchmen

**16:14** · to help you in battle that will appear sometimes just when you need them um now player destroys an elf Shrine no ding because you actually haven't crossed the threshold but you're moving along the bar so it's still good but you haven't hit an actual threshold for a thing now you you like start hanging out with the eles and you um oh no that's the wrong thing oh

**16:35** · no no sorry my like um you you help build his Temple to the old God said he likes ding he makes a special item for sale I I think you get the idea um now on the other side you start hanging with the elves and maybe you come you kind of like one of the elves and you do a quest for one of them well Frank's going to hear about that unding you know his his

**16:56** · micro passion of elves will move back a little bit and maybe enough to actually affect the macro passion bar and that special item that was on the Shelf goes off the shelf cuz and he will reflect all this in his dialogue with you yeah dude heard what you did with the elves not \[ \_\_ \] cool um you know feeding this back is all really really important um I'm going to take a little um side step here and talk about zero sum games and they're going to be very important to what we're talking about here you may be sensing this already um

**17:26** · $10 to anybody who spots the math error um which I forgot to fix um so zero some game is say there's 10 gold and Ken and Pierre both want the 10 gold and either can and you could have a bunch of situations I got 10 he's got none I got zero he's got 10 I got three he's got seven I've got six he's got five

**17:48** · um drama major um but it's a zero some game meaning he gains I lose I gain he loses then there's nonzero some game games um I'm going to use Lucky Charms because I like Lucky Charms as an example say I've got a a surplus of blue moons and Pierre has a surplus of pink hearts more than we can possibly eat but we really both want we want the variety it's really important for our economy we can trade so I give my

### Lucky Charms Relate NON-ZERO SUM GAME

**18:17** · Surplus to him this is this Classic this is what trade is right he gives me his Surplus and now we both have much better economies because we have this mixture of resources we need that's a nonzero game zero Su means you can't please everyone and we're going to leverage Zero Sum in this design substantially um so for instance Frank

**18:40** · and Pete hate elves player helps Romeo the elf and the and the and Frank and Pete like you less so the elves like you more that elf likes you more maybe other elves like you more but they're going to like you less Zero Sum but there's even a zero sum between

**18:55** · in in villages themselves Frank the orc loves the old Gods well Pete the orc is a cleric for the new gods and every time you help build the old God Temple you're going to piss pee the orc off now you can trade them off against each other because remember these aren't unilateral each character has three or more passions so you can really piss peed off

**19:15** · in regard to the temple but you can help them out in other areas and you going have to balance all these things off one another but they're all going to be transparent to you and we have to have a limited number of them so you can really track this all so it just doesn't become a giant spreadsheet that overwhelms you you but you know as I said you're D if you do if you D if you don't let's talk about the love that dare not speak its name so orc and

**19:38** · elf we have Juliet the orc is in love with Romeo the elf um now most of the Orcs want bad crap to happen to the elves except for Juliet so you can go all day and pound on the elves and all the Orcs are going to love you but you're going to be pissing off Juliet so she's for instance the Priestess in the Temple when she gives the healing well she's you're going to have a hard time getting that healing from her um

**20:04** · but if you help Romeo she's going to her appr is going to go you going to go up but there's going to be a lot of Orcs who don't like that so even within Villages they're not they're not a monoculture they all have different hopes and dreams and feelings um so we talked about characters um you know why are there only five characters in each City well there's going to be a lot more characters but there will be what I call drones and they're very simple they're macrobar they just have a macro bar is a function of all the other of the stars in that Town's macro bars and basically

**20:34** · they're just going to be guards and hirelings and Scouts and spies and foragers and um and shopkeepers who aren't complicated but they just they just sort of feel generally how the town feels about you but they won't be able to give you the kind of benefits that the Stars would be able to give you so that we'll populate the world but not with millions of stars um I won't go too

**20:53** · deep into this slide but there's like whole list of things you can accomplish for people um You probably see them a lot of them in other games some of them could be new you know worshiping Gods killing people rescuing people collecting resources destroying resources and then rewards that these Stars can give you price adjustments combat help they can give you Buffs they can help you build new buildings which give you other benefits they'll loan you equipment they'll give you equipment they'll um you know we'll send henchmen to help you um and um and then punishments the same

**21:25** · way they can do all they can do all the negative they can raise their prices they can Bargo items to you they can debuff you they can send out hostile drones to get you all kinds of crazy stuff but this is a list we just keep growing and growing and growing but they all all of these have to come off the macro bars which are a net effect of the three of the three Um passion bars all right so let's talk about a dramatic event so we want in this world

**21:52** · like I'm speaking very generally about stories so far and this conversation will stay pretty particular in general about story you know the go obviously we're not this is not at the level of a Last of Us story here I'm talking about or a Bioshock story we're trying to keep it um very simple but I want you to keep

**22:10** · in mind that the goal eventually will be once we have these systems in place to actually apply real interesting meaningful story but the system comes first so let's talk about an event a very traditional event here so we know authorly that and we feedback to the player that if if there's a two orc Stars disapprove of the player and any any three other stars approve of the player on their macro bar to a certain extent a red dragon will appear in the world and the red dragon is what we call an unaligned star he has no Village all he cares about is death and destruction

**22:42** · it's all he cares about he doesn't care who you do it too he just wants him dead and so he's got a macro bar and you see he's got all these things he can do for you all those black lines on the macro bar and the more terrible things you do the more ding the more stuff he gives you he shows up in battle to help you know you kill Orcs then you kill some Elves and you burn down their Village and he gives you a kill base buff and

**23:04** · then you do what you do so many terrible things you start a dwarf and goblin war through a series of quests and now he says dude I will destroy any town you want from me just give me the word and I'll go kill it and that has obviously a major effect in the game that kills a bunch of stars really changes the battlefield but that's the that's the end game with the with the red dragon but it's also a silver Dragon if you remember your D and Dragons the metallic dragons are nice and the color dragons are bad um at least that's the way my in

**23:33** · in uh when I remember it so the Silver Dragon only wants you to do constructive things he doesn't care for who he wants you to help he wants you to build he wants you to craft crops he wants you to all those nice things um that you want to punch him in the face sometimes he's so nice but there is a zero some game

**23:51** · and obviously he's got he can give you a whole bunch of stuff but there's a zero some game between the red dragon and the Silver Dragon so as you're making one of them happy you're gonna piss the other one off and if you get a dragon if you get one Dragon really happy at you guess what the other dragon's gonna be super unhappy with you and I don't need to tell you what happens after that so there's this complex web of sort of

**24:13** · alliances allegiances um different feeli you know even and Villages aren't holistic and and and and and you know they have different people have different feelings within Villages and you're going to have to either when you go into the game play them off each other you're going to have to decide make some decisions I'm going to be Mr orc this time I'm going to totally hook up with the orc Village but that means you're not going to get a bunch of things in other Village or you're going to play them all off against each other or you're going to keep both dragons sort of you know in

**24:41** · the middle but you're not going to go too far with either one of them or you won't interact with them at all these will all be choices in the game and then you throw in more factions yeah here's the dwarves here's the Goblins all with their stars all with all with their drones and and and they all play into the other systems they all speak everything every new thing you add can speak to all the other things that exist now let's talk about an event not the really original event from the north comes hordes of white

**25:09** · zombies now that has a net effect of adding a passion to almost everybody in the world which is holy \[ \_\_ \] I'm scared of the white zombies and that's going to so no matter how they feel about each other and that was you know if you if you look at Game of Thrones you know the

**25:25** · um the uh Knight's watch went around to all the kings and all the can they said hey help us with zombies and only one of them showed up you know but they all cared about them to various various degrees so you're going to have different passions but maybe there's going to be a dwarf of necromancer who's like well this is awesome I love the fact that these guys showed up because I'm a necromancer um and so these major

**25:46** · events can change the the ground underneath you they won't change the existing passions but maybe they can add new passions um and give you a different way to influence people because new things have happened in the world all right so as I said before I hinted at before none of this is like Earth shattering from a oh my God that that's an amazing narrative um but it's about

**26:06** · the opportunities and it's about opportunities to make this replayable narrative so we we had to build a system first and this is what this is is building the system independent of game it applies this could apply to a first person game this could apply to a fantasy game this could apply to an RTS the system really can apply to pretty much any game um but I gave you sort of an example of of of of an RPG but you're building a web of nearly infinite relationship States and these states these changes in these states is where you'll fire off our TM professionally

**26:38** · crafted well- written well- acted narrative and dialogue but they will be they won't spawn off trigger points in the world they'll spawn off a Confluence of all these things H interacting with each other so you know here's a bunch of characters saying a bun saying a bunch of things um that will be you know obviously it's all placeholder dialogue still but they are saying uh except for OMG that will be in the game um they are say you know they these are spawning off of what you do and and and as their you

**27:07** · influence their passions they will react to you um let's go for a detailed example of sort of a story that can form around this um there's you there's a dwarf named Betty and an elf named Veronica um they are both have each of

**27:24** · them have a passion and please like this mace like not women looking only to get married and this is not like I'm not making a statement about sexual interactions here this is just a Betty and Veronica example pretend their dudes um and um say they're both looking for marriage and with you so that's her

**27:45** · passion now you start interacting with them you start doing things to impress and make and build a relationship Veronica so she says I'd really like you to meet my parents you have to that's a quest you have to go to this Quest fight a bunch of monsters steal a bunch of crap craft some flowers you know craft a a bag of donuts or whatever um and bring

**28:06** · it to her parents that quest one boom um you that makes um her passion for you grow and her macro bar starts to move and she's like oh thank you for meeting my parents here's a 10 plus 10 sword athal sword um then you uh you craft

**28:23** · Betty a house um and she likes that a lot um she gives you she gives gives you a buff that gives you plus 10 approval to all your actions um in the in in in her town in the AL town so every time you get a every time you do something for somebody else they're going to enhance the effect of that because Betty's saying nice things about you and we'll support that with content she'll be walking around town saying how awesome you are singing your praises and you'll see people react to that and we'll reinforce that with the game system um now if you step back and you

**28:53** · look at Betty and Veronica well they're not just two different women they're marrying them will yield very different effects um really Betty's about crafting Betty's about um Betty's about building Betty Betty's about um crops Betty's about sort of earthy things and Veronica's more royalty and she can give you like lots of nice weapons and

**29:17** · treasures and castles and things like that and you're looking at them you're like okay well you know where's my strategy here as a gamer how do I want to approach situations just like any character decision you make in a game but you're gonna have to decide you can't marry them both so you're going to have to decide and in this case let's say you choose Veronica um and you decide you

**29:41** · want the combat benefits so you really start pushing on her you build her an enchanted garden and that's like that moves her macro bar up to the point where she unlocks the wedding quest for you um and the wedding Quest is craft a tuxedo build a chapel get the priest's macro bar to a certain certain place where he's willing to marry you by doing a bunch of crap for him uh in any any of his passions it's not just one Quest getting all his passions to a point where the macro bar yields he's going to marry you and then you go on a quest to a dungeon to find the ring that she wants um Step Ahead for a second now but

**30:14** · remember as you're pleasing Veronica you're pissing off Betty because she still has hopes for you but that doesn't mean that you have to go on one track and commit to it you can waver you can go back and forth and you can take your time and de side but you know that that can have negative impacts because she's W they're both watching what you do and they're pulling away for you or ping towards you um so when you complete the

**30:39** · quest you finally said well I played I I I let I let him I let Betty on along enough I got to finally you know put a ring on it I'm G to marry Veronica and you do that and ding that moves her macro Bard point where she gives you a combat buff a permanent combat buff a th000 gold and a castle um and a castle gives you all these other benefits for yourself um but Betty Betty is unhappy with you so she removes the buff from you that enhanced

**31:07** · um you know say your crafting abilities um before um and when when she hears the marriage and it really sinks in and and you haven't done any you remember you could still make her happy somewhat by doing other things on her passion line but say you don't do that and she really goes negative on you she says well you can't craft crops in the Dwarf Village anymore and that's a real problem for you because you really wanted that but you made a choice you made a choice and like a big boy you got to live with that choice big boy or girl you got to live with that choice but here's a

**31:37** · Twist we will write different characters for these people we will give them their own hopes and dreams their feelings you know you know they are different characters we've written lots of different characters there showan and Elizabeth and and um Andrew Ryan they all have different characters that are basically independent of any game systems and people like them or hate

**31:55** · them or like spending time or don't spend time with them well independent of how you feel about them systemically you're going to feel about them hopefully if we do our job right as people so you may marry Veronica you may like Betty a lot more and um you're going to have to live with that because you're going to have to spend a lot of time you know she'll go on quests with you and things like that and spend time with you and interact with you you're going to have to think about that the player is going to be sort of CH making choices between what he wants sort of you know what character he likes what character he likes to spend time with him what he needs to grow in this game

**32:25** · um fortunately unlike life you replay it and marry the other one next time um so with good writing hopefully players should be able to make to have to balance physical gain versus these emotional fulfillment decisions and with all these systems

**32:41** · your ability to play one off the other the ability to you know kind of keep people happy but where these people kind of happy those people are really happy but by betraying friends they've had moving their macro bars down there will be false friends leading people on betrayals and reconciliations you know you could if you do your job right end up simulating something along the lines of this um or any other any other sort of

**33:06** · narrative experience where you have lots of people who are plotting against each other and playing one off each other um you could make you can make I think you could re with within grasp start to try to stimulate something like that but driven not by your TV set driven by you

### Still Waters Run Deep

**33:22** · um let's talk about um hidden passions hidden passions so characters let's just say arguments that have three passions at the beginning but maybe they also have hidden passions which are not revealed at first um these are a resource knowing about people's hidden passions means you can impact upon them in different ways if you don't know about the passion you can't impact upon the passion um and it's a resource that

**33:46** · other characters characters can give you about themselves depending on their macro bar or you they can give you they can give you gossip about characters they know um so let's say you've been F you've been friends with Romeo the you really grown his macrobar and one of one of the thresholds is hey I have I know about this cool Quest why don't you come on it with me and we'll share the riches

**34:05** · so you go on the quest with Romeo and he like tells you all about himself about his hopes and his dreams and how he really strangely hates dwarves in a creepy way and he tells you he writes poetry and he reads you some of his poems you really get to know him and you're about to go in the dungeon and you go down the dungeon and you sort of

**34:24** · help him on the quest complete the quest that moves his macrobar to another state stage Ding and he says I'm going to reveal to you one of my secret passions I'm in love with Julia the orc and so now you know a new passion about Romeo because you spend time with him you've interacted with him and you've given him what he wanted on his bars and

**34:44** · um now You' got to make a decision because you know now that he's not going to like it when you when you beat up on Orcs because um he's in love with Julie at the orc so you have to make some decisions do I continue this friendship with Romeo do I do I abandon the orc like what do I do here um and um so you can see has a new passion here um so the orc

**35:08** · reinforcements come in in this in this dungeon and boom one of them is Juliet so now you have to make a decision about what you're going to do obviously he's not going to kill her what do you do um but then you're say you're on the same quest with a different character he doesn't care it's just me let's go kill all those \[ \_\_ \] um Okay so replayability

**35:28** · and that's Central to this um games we made generally have had to add ons I'm very fond of them but they're add-ons they're not addins you add it to the end of the experience games like Civilization XCOM add in to the situation allow allow you to start the game over and play a very different feeling version of the game so obviously the player will have each play through they can choose different stars to befriend different different people to take on board different people to turn against and that's player driven um um

**35:58** · they can um support the same characters but to different extents um then let's talk about the passion pool okay so let's say Frank the orc actually has 10 we write produce record cast 10 different whole passion sets for him but in each game we only reveal we only get

**36:16** · three we choose at random three of them so like we all have different stages in our life where we care about different things you're encountering Frank at a different stage of his life he's still the same guy still the same character but at one point of his life he cares about hating the elves who Temple the old gods and he wants to woo Barbara but then he's married he so hates the elves

**36:35** · and but he's his marriage is not going the way he thought so maybe he secretly loves Romo the elf and you know he's he's he he wants something different in his life now and he also is you know he looking to his retirement he really wants a pieces of the cat's eye Medallion and so he's a different guy

**36:50** · this time and he maybe have other secret passion so that's you know when you come into the game you'll still see the same people but though they may have different goals um and of course we can make over time new passions new characters new quests new factions all those things available as time goes on um so for instance you add a new faction the werewolves the YC does not like werewolves but one of the else has a thing for one of the werewolves so these are new passions you can play off and the werewolves have their own passions of course um okay and this is not a promise

**37:23** · of any kind we have no idea whether we're doing anything like this but let's talk about Co-op multiplayer say my brother and I are playing the game together and we have in real life we have a great relationship but we come across some Elves he's done a lot of work befriending the elves he spent a lot of resources befriending the elves the elves hate me hate my guts and they

**37:44** · see me and they start I get ambushed by the elves because I pissed off somebody's macro bar to a certain point where they sent an ambush at me and I'm on you know I'm on you know the headset with my brother he's in New Jersey I'm in Boston and I'm like Stu come on the elves are talk me help me out he's like well I don't know I really those elves are been pretty good to me so sorry

**38:06** · Ken um and you know I'm dead and he's like hangs out the elves and you know we may we if you ever play diplomacy which one of my favorite games of all time you know the effects of some of these betrayals that can happen in games um one of my dearest friends in the world I still kind of hate because of a game of diplomacy because it's the game

**38:29** · relationship versus your personal relationship so all these relationships if you bring real people into it I think can really expand to a whole new level and that's it um

**38:52** · questions um start there in a lot of what you said um the NPCs were aware of all actions that were taken by the player how will things like lying and um taking actions in secret be managed and this kind of system I I haven't I think it's a really good question I think that's beyond the scope of what I thought about yet I think it's something you could it could complicate things it could also be a really cool thing but I think that how information gets propagated maybe we need some kind of

**39:20** · feedback about information propagating throughout the world maybe have some ways to keep information from propagating maybe there's tools you can have for that I think that it's a really interesting space I just haven't thought it through yet but it's a good question we'll step to through hi there so um one potential issue I can see with this is that a lot of times in you know stories and TV shows the most interesting things are when a character feels very conflicted about another character like for example when when Deborah finds out that Dexter is a serial killer sorry spoilers uh she's conflicted with her uh

**39:52** · police values but also with their family values and it seems like with your system would still have a sort of commentator explosion of uh sort of Art and voice acting and writing because you need to sort of consider all these possibilities of every passion that each character might be in not just the macro passion but also the specific states of

**40:15** · the non-macro passions yeah I think there's a I'm not in any way pretending there's a there's a trivial amount of writing work to be done here I think there's a substantial amount of writing work the difference is because they bounce off each other and they can they play off each other they're reusable and they and they can appear in different games they can appear in different context but there's still a full plenty

**40:36** · big writing job to be done here I'm not trying to write less I'm trying to write stuff that can be reused and replayed in different context but you're completely right and starting to track that combinatorial explosion is going to be I think one of the first steps when you start doing the math to see how much stuff you can really support but writing is relatively cheap it's what I what

**40:57** · excites me about this is the fact that it's different and it's driven by the player so you know you can you have to scale that to taste and and what you can afford gota thanks thank you hi uh system sounds very interesting the you know likeability of a star towards a player made me think a bit of Dragon Age Origins and something that was kind of a let down in that

**41:22** · system was that I was never motivated for a character to dislike me other than you know player impose narrative yes my guy's a paladin type character I'm not going to like the witch y but in the end I needed everyone to like me so I can get the benefits from them liking me so on so forth so I had to do actions that kind of went against my character to fulfill the game needs how do you plan on balancing that

**41:50** · or giving positive rewards for some players disliking well I don't give I don't think positive rewards for making people hate you is I thing I think the zero some game is where that comes in cuz like I was talking to a friend of mine about he worked on a game um created a game called dogs he's right there um and

**42:10** · you know the dog would like you or not like you depending on different things but because the dog was the only actor in the world you had that challenge exactly what you're talking about is like what's the you're not going to kick the dog in the face you know so like how do you how do you deal with that and that's why the zero some games are so important just like real life you can be nice to somebody all day long and just by being nice to that person and ignoring the other person hey you're you're doing gay development and your wife's at home waiting for you ah zero some game and that's the problem that I

**42:38** · think we want to highlight because I don't think the choice of Good and Evil to me is always that challenging thing is like well I don't want to be a jerk but just by what you don't do or what you do for others makes you a jerk to some people because they don't like it hey you went to dinner with that guy \[ \_\_ \] you um and I think that's the heart of how you deal with that problem okay thank you it sounded like um sort of sorry

**43:02** · about all the cursing by the way I'm bit foul it sounded like um your your sort of stars were fixed characters even though they were going to have like different passions every time you restarted the game sounded like Frank the orc was always going to be the blacksmith in the shop maybe I didn't get that but um so I was wondering what are your thoughts on sort of having Stars emerge based on who the player wants to interact with so I I think that

**43:26** · I I mean one thing I like about these sort of replayable games is they let you set all the sliders and all the variables so you know I don't think I'm and a lot of things get trickier once you have things like leaderboards and achievements and stuff like that but you can invalidate you know those things for the purpose of a game but I'm really a fan of saying I want to play a game where Frank has these passions and this guy has these passions if you want that because it's your game and the system unlike where you can't really do that in a game like infinite right um this game I think would allow for that so I I I I

**43:54** · support it in concept absolutely because I that's the kind of games I love I like setting every little check boox myself makes my makes it the game mine um so it seemed like there's a might be a bit of a disconnect between the interesting dynamics of each Quest and the somewhat selfish rewards you get for it possibly a boost for a main quest

**44:19** · how do you think this game would work if you eliminate these reward boosts or even eliminate a main quest and it was and these Quest were the entire game so I don't actually like so main quest is a really interesting question I don't do you need a main quest I don't actually know we've been talking about that like because a main quest implies a macro narrative that moves on and macro narrative fights against this sort of

**44:45** · experimental game like you know again going back to civilization there's a macro narrative in the sense that you have five six different and actually had a bunch of slides about this but I thought it was beyond the scope of the talk like wi conditions and things like that potential wi conditions I thought that was a game design not a system design so you could like say I can win

**45:04** · The World by destroying one of the villages I I can win the game I Destro one of the village I can win it by making them all like me a certain amount you know by whatever you know you can set different wi conditions or you can sort set a macro story but I much rather have these events that happen that change the Dynamics like the White Walker example I gave than enforcing a

**45:22** · story now again I don't know if that's going to work like you know and I knowing my myself you know you can you always get drawn into what you know and what you do so what we're that's why we're sort of really trying to you know reset here because we've done the same thing for so long so I think there's my discipline is to always try to start with what do we need to make this a great game and right now I don't know if that's a macro Story the stories may all come out of these entirely player-driven

**45:52** · experiences so uh how are you modeling uh the passions um there was a talk from the AI Summit two years ago by Stefan buau from story bricks that St yeah presented kind of a great way of modeling passions I was wondering how close it is to what he was talking about so I savan is one of those people is out there that is thinking about these things and we've had a bunch of conversations um and I think that you know what I like about this is that there are people and you know some other friends of mine in the industry are talking about this um what I the sort of

**46:22** · the place where I've been thinking and we're actually going to get together later um that I've been thinking since I last talked to him I sort of really focused on um my focus has been on making rather than making characters of the range of emotions making a character with very few passions these three passions and all these zero some game situations because I'm probably less ambitious than he is to some degree um

**46:47** · and really and as a writer I'm like how do I how do I make characters come out rather than people come out so I think that's really where the direction I've been going in that look that could all change he may we may sit down have a lunch later he be like you're a \[ \_\_ \] idiot let me tell you why and this whole talk is a waste of everybody's time um but that's where I since our last conversation a couple months ago that's where I've really been going with this and you know we sort of he and I have both been tun I found he called me after

**47:12** · like oh I I talked I announced this talk he's like I've been working on something very similar so I think this is one of reason you want transparency here you want openness is you want to be able to talk the reason I'm doing this talk is you want to engage everybody's brain because I think it's an important problem I I think it's hard to say hard to deny it's an important problem and the more of us who are thinking about it and that's why I wanted this you know out there and it's pretty early is so we can have lots of smart people like Stefan and you know talking about this

**47:44** · thanks uh hi hi what about uh modifying passions what if you could do something to convince Frank that elves aren't actually so bad it could still be zeroone because now the other works really hate both Frank and you yes so I think that's a possibility like my sense is that it I'm I'm not ready to

**48:04** · play the drum fills yet you know I'm sort of getting the Rhythm down and so I think that's you can there's lots of ways to play on the system and to interact with the system my first step our team um I'm talking to to Eric Erland who's our leite technology guy about this a lot is like I think the first step to modeling this is you design a paper and Pen Adventure you use D20 system right you set up a bunch of quests you set up a character's passions and the only thing you use a computer for in the first test is to track the

**48:31** · passions and the macro passions and the and the interactions of those because that's a lot of data but you could just with pen and paper start to play out this system and see how parsable it is and see how it works and that's probably our first step before we even really touch a computer you you could probably do this in a database application um and then we will we'll

**48:50** · build from there but you know the options to expand upon it and play with it are infinite presuming that you you know don't Overflow what I call player Ram like how much how much stuff can they keep in their head at once and it may be a great idea and you may play with it well just like all these ideas it may be a great idea you may play with it it may be a terrible idea it's hard to say until you try it but that's one of the goals is it's a starting point

**49:13** · right yes um so I'm a designer on the civilization franchise I wanted to say how excited uh designer on the civilization franchise well I a fanboy yeah I'm I'm happy to hear that yeah we're big fans of your work as well and it's exciting to see your approach um one of the things the macro sort of mood modifier reminds me of especially is the sort of opinion system that we use in Civ and um I think the examples that you

**49:36** · used um are definitely the most most colorful and interesting and kind of prone to narrative um flavor when you know you have the one orc feeling this way and the other orc feeling this way and kind of like aligning the passions in such a way that that the player Works towards um you know them really liking you or really disliking you and I was wondering um if you had thought about or if you have any um ideas about how to kind of avoid um a lot of the NPCs

**50:00** · ending up in that kind of like middle gray space because like you there are ways to solve it with like the comori uh writing explosion of like yeah maybe you built the temple for the old gods but you did elf Quest so like you're in this neutral state with this NPC but it's kind of hard to reflect I mean to me that's a balance problem because what you the rewards in the middle space are going to be pretty marginal right versus

**50:20** · the big rewards you're going to have to really take some big Swings with people so you want gameplay to kind of Drive players towards the edge so so you can keep you know getting 10 5% price reductions at the store from everybody it's not really going to move the needle to really accomplish those larger Quest um sorry um to really

**50:37** · accomplish those larger Quest you're going to have to get people really passionate about you one way or the other and as I said the zero some games is going to lead to you make some real friends you're going to make some real enemies yeah and the transparency will help players get there exactly cool thank you thank you well thank you for the talk uh you talk a lot about how it's very player focused all the the actions from the player those decisions but you also mentioned these hidden systems that you uncover um by having these relationships and I'm curious in

**51:06** · minimal interaction what happens when you see a confrontation and you step back um do the AI find out hidden passions of each other on their own uh what happens if you hide in the bushes during the events that are occurring so a a passion remember is as far as I think about it at this early stage age is only what a character feels about a situation relationship to you and that you can impact upon so I mean the notion

**51:36** · of a player knowing about another player a character knowing about another character's passion is relevant in how they talk about them you know we can you know make colorful stuff yeah I heard about Romeo he's got weird tastes you know um or as I said that he can reveal

**51:52** · potentially if you one of people's maccro bars could be revealing passion a secret passion about somebody else and that just basically is another meter you can push on for them so I don't know if it's meaning if there's like game there's you know systemic meaning in what you're talking about I'm not saying there couldn't be but as I'm thinking about it right now I don't think it's I like we when we did this thing and and a bunch of us worked on it what we kept coming back to was it's very easy to step out of the system and start coming up with is that five yeah come up with

**52:25** · narrative things that could happen but we kept saying no no it has to come out of has to spawn out of this system and so you don't want to just Ser saying oh these guys start feeling this way about you but independent of the passion system because then you're just you know throwing you're just sort of throwing artificial things into the mix you're throwing in hacks basically and we want the system to work at a core basis not saying we can't expand the system but we want everything to be driven from the core system thank you thank you hello um

**52:52** · my question is about player choices and like um I was wondering like um there for every simulationist or narrative driven player who's all about like portraying the character in an RPG there's quite a few more who are playing the game mostly because they maybe like the choice system and they like how the system enables them to basically kill everyone and they care not for who the For Whom the blood flows but I was wondering um how would you handle a dark question yeah um how would you handle

**53:22** · incons inconsistent player choices in delivering in delivering a coherent narrative experience through a system without necessarily using a zero sum game so I think the biggest problem is going to come out with thresholding back and forth between like if you're constantly moving somebody back and forth towards a feeling towards you you

**53:41** · I think that you you may find your you know what I'm talking about like well I did this thing he loves me now he closes this store now he opens this door now he closes this door well you could reflect that certainly in dialogue like dude you're driving me crazy but you could also potentially start putting in modifiers like once once you get past a certain threshold you know on a positive it's harder to make them dislike you you've built up credibility and trust with them but that would have to be transparent and systemic um and I think

**54:07** · you may want to do that to avoid situations like that and when somebody hates you you really got to work but you can get them back but you really really got to work we had a notion of locking at the end that you couldn't come back from it and I think in my experience you know that's probably less interesting that if there's a way to come back to with super hard that would be kind of cool that person probably always carry you know that negative um mathematical

**54:34** · twist we put on it will come across a narrative like yeah you know okay but I still don't trust you you know where if they got to the same point without going so negative they wouldn't have that I sit on trust you line they would just be like okay well okay I'll do this thing thank you thank you hi um I was

**54:52** · wondering when would you think to input an end game of this system like and what would you do for the player at the end would it be a Fallout style like recapping of all the relationships you built or I I I think that's probably beyond the scope like of what I'm talking about because I think that's a game that's a game design decision like

**55:11** · a a particular game where this is a system like you know how do you want to end it there's a million ways you can end it I don't actually think this dictates any of those things you could you could have a bunch of narrative events you could have when certain thresholds are like I said you could have when certain towns were destroyed there's a million end games you could do I think that's not what my first priority is so all I can do is beg ignorance on this one and say that's something for the down the road yeah so I've thought about similar

**55:38** · systems quite a bit and I find it very interesting but one of the conflicts I always find with it is that it seems very hard to design a sort of deeply thematic narrative that deals with these types of open-ended systems um given that you've dealt a lot with deeply thematic n Nares do you see a solution to that or do you see these as sort of mutually exclusive types of narratives um I

**56:04** · think it's a really good question and the honest thanks the honest answer is it's it's hard to say and that's part of the experiment like I I want to get up here and say like we could definitely have the best of both worlds right I don't know if I can say that yet because in the same way like Civilization has a narrative right it's this meta narrative

**56:25** · Sports have a narrative like when you play when you play a football game there's a bunch of rules but it it not only has a narrative it has a meta narrative like well that guy just left the Giants and now he's on the Chargers at a team yeah is that right and but and so he's got this rivalry going so there's this meta narrative and he and he just \[ \_\_ \] that guy's wife and like oh my God what's going to happen on the field um so there's a meta narrative

**56:48** · around those things and I think there will be a narrative that forms in this much more supportive than a civilization because of all these characters and the dialogue and the ability to have you know a multi multirack feeling characters having multi-track feelings about you I think that's going to be a very interesting question that's going to be the goal and we're just going to have to see how that plays out um hopefully it's a really

**57:12** · good question but yes it will totally buy it yeah so the world that you describe here would only change if the player decides to do something to change it um but like something that for instance uh stalker in my opinion did really well or

**57:30** · in a really interesting way is that things happen even without you doing anything uh about it the the the world itself is alive and changing uh even when you're not there yeah uh how would that like how would you implement that in a system like this so the White Walker example I gave it's an interesting one of that could be something that spawned off of a bunch of things you do or we could just you know sometime roll the die or plan or or authorly plan on it to happen

**57:56** · and you see a lot of there are a lot of board games actually where events happen like xcom's a great example where they sort of put a new template of event that comes in that changes how you have to play so I I don't know yet I think it will allow for either one I want to make sure the player feels that they're drive that they are at the helm on the other hand you know like

**58:15** · um um you know I was talking to to my friend Drew yesterday about Ned Stark you know and how Ned thinks he can play everybody off one another and everybody he can keep everybody happy and he finds out what happens he tries to keep everybody happy and then you have but then you have situations that happen outside of your control and I think that that is something interesting if you look at Game of Thrones that always happening people think they have things in charge and then Tyrion comes in and shoots you in the gut with a crossbow um and so I

**58:41** · think you have to balance that to make sure the player still feels that they are the driving force in the world but maybe you do want the white walkers to appear by the by you know Fiat all right I think that's all we can do right now thanks guys