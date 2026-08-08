---
title: Emergent Storytelling Techniques in The Sims
source: https://www.youtube.com/watch?v=YjuOSgPdtS0&t=2246s
author:
  - "[[GDC Festival of Gaming]]"
published: 2020-07-03
created: 2026-08-07
description: In this 2018 GDC session, Maxis EA's Matt Brown examines the various techniques employed across all four generations of The Sims to empower player-driven and emergent storytelling. Join the GDC mail
tags:
  - clippings
modified: 2026-08-07T21:18:46+08:00
---
![](https://www.youtube.com/watch?v=YjuOSgPdtS0)

> 中文翻译整理：[[模拟人生 涌现式叙事技巧]]

In this 2018 GDC session, Maxis EA's Matt Brown examines the various techniques employed across all four generations of The Sims to empower player-driven and emergent storytelling.  
  
Join the GDC mailing list: http://www.gdconf.com/subscribe  
  
Follow GDC on Twitter: https://twitter.com/Official\_GDC  
  
GDC talks cover a range of developmental topics including game design, programming, audio, visual arts, business management, production, online games, and much more. We post a fresh GDC video every day. Subscribe to the channel to stay on top of regular updates, and check out GDC Vault for thousands of more in-depth talks from our archives.

## Transcript

### Introduction

**0:05** · Uh so, welcome everybody. Uh uh I know it's probably been a long week and it's first thing on a Friday, so if you're not hung over, you could have been sleeping in anyway. Um so, uh I'm supposed to tell you to silence your cell phones if somehow you haven't heard that already uh this week. Uh and uh there'll be a survey that you'll get and say nice things. Um the Uh so, I'm Matt Brown. I'm the studio creative director for Maxis. Uh in a previous life, I was the technical director and designer for Sims 2 and the creative director for Sims 3.

**0:38** · Uh so, I spent a lot of time, several years, with these little people in their little houses with their little jobs.

**0:45** · And uh I spent countless hours arguing about urine.

**0:52** · Um and uh uh and when a Sim pees themselves, uh what color should the puddle be?

**0:58** · Um uh turns out not yellow.

**1:01** · Who knew? Um and if the if a Sim does pee themselves and they leave a puddle, should dogs be able to lick it up?

**1:08** · And should toddlers be able to play in it?

**1:12** · Uh and if they do play in it, should we switch them into galoshes and a raincoat?

**1:16** · Um seriously, it's a weird job. Um so, I want to share some of that uh with you guys today.

**1:23** · Uh not the urine. That would be weird.

**1:25** · I'm not going to share urine with you.

**1:27** · Um the uh actually, there probably is urine in this talk. But anyway, um the Uh actually, now I've said urine so much. Um So, Uh so, now while the Sims started out as a behavioral simulation, uh the over the years, it's definitely become more of uh what we call a storytelling engine. Um largely because that's the way the players play it. Um and uh as designers, we've embraced that and um we, you know, we cater a lot of our design thinking and our design uh design systems and patterns um towards storytelling.

**1:58** · So, for the rest of this talk, I'm going to walk through several of the techniques that we that we use to facilitate um those sorts of stories and to enable more player agency in telling their own stories.

**2:11** · Um but before I get into the actual techniques that we use, um I want to walk through a really brief overview of sort of key design philosophies as a bit of an explanation of how the core behavioral AI in The Sims works um because a lot of our design patterns rely really heavily on that. Um most of you probably are familiar with this if you've heard other talks in the past or read articles, so I'll go pretty quick.

### Nurture

**2:34** · So, The Sims is fundamentally about nurturing. Um we want players to feel compelled to take care of their Sims. Um we want them to feel like the Sims need them.

**2:42** · Um and generally speaking, the objects and the interactions and such in The Sims are grounded in reality, uh and we take liberties with culture and the time frame, but for the most part, the world is something that players are familiar with.

**2:55** · Um and we give The Sims similar motivations to actual humans, and I'll get into that get into that in a minute, um so that the player can relate to them and understand them.

**3:04** · Uh and then we make The Sims imperfect.

**3:07** · It's already urine. It's not even It's like the first slide. Anyway, the uh the uh and the The Sims make mistakes, and that's very intentional. Um and they a player instinctively knows that because they can relate to The Sims, and that makes them want to help them. Um and if a Sim pees themselves like this, um you don't need to have peed yourself.

**3:24** · I mean, maybe you did, but you don't need to have done that um in order to empathize because you can relate to them.

**3:30** · Um because people are parents.

**3:32** · Um if you're literally a parent or even if you're not, it's in us, um and we manipulate that on The Sims cuz we're dicks.

### Hierarchy

**3:41** · Um Now, back in the '40s, a psychologist named Abraham Maslow uh proposed a theory of human motivation that known as Maslow's uh hierarchy of needs. And it's basically uh smart guy way of saying first things first.

**3:54** · Uh in essence, it says that human beings need to satisfy basic primal needs before they can move on to higher order needs. So, I need to feel physiologically stable. I need oxygen, water, food, clothing, so on. Basically, things that if I don't have them, I'm going to die today or tomorrow. Um before I can start thinking about higher order things, um which Maslow called safety, but really what he's talking about is your career, your your credit card balance, your 401k, things like that.

**4:16** · And until I have those things under control, um uh I can't really start focusing on my relationships, my family, my friends, my my being part of my community, and so on.

**4:25** · Um Now, in The Sims, we don't generally go into these upper levels um of esteem and self-actualization and more heady things. Um although, there are some systems like building skills, learning to play music, learning to paint, things like that um that touch on this a little bit uh because you can't actually focus on those until you've dealt with those lower level things, but they're pretty shallow, generally.

**4:44** · Now, everybody knows this, I'm sure, but that hierarchy is represented pretty literally um in The Sims as what we call motives, um hunger, bladder, energy.

**4:52** · They're basically values from 0 to 100.

**4:55** · They decay over time, and you can fill them back up by performing actions uh on those objects or on various objects.

**5:02** · Now, on the surface, that doesn't seem like it has a whole lot to do with storytelling, um but uh but a primary component of storytelling in The Sims is relatability and casual understandability. Um uh because at least theoretically, all humans, and by association, most Sims players are uh are doing this their whole lives. Like, they're you're we're on this pyramid, this we're on this hierarchy, and we're trying to get as far up it as we can.

**5:26** · Um and uh that means the players can kind of immediately understand the Sims thought processes, um and what's expected of them, the player and the Sims.

### AI

**5:37** · Now, in The Sims, the AI is grounded in that theory, in Maslow's hierarchy. Um I usually refer to the AI in The Sims as big A, small I, uh because it's marginally intelligent and it's really really artificial. Um Uh but in many ways it's that simplicity that makes it possible for so many behaviors to work together and for emergent situations to arise.

**6:00** · Um and the way it works is essentially the Sims look around the world uh asking objects, you know, what affordances they have, um what interactions are possible. Uh we say that those interactions advertise to the Sims uh telling them which motives will be satisfied and how by how much and and so on if they perform those interactions. So, real quick, for example, if you have a toilet, it might offer use, flush, clean if it's dirty, repair if it's broken. Um fridge might offer to have a snack, cook something, the bed might offer to nap.

**6:25** · Um and the Sim then scores all of those possible actions based on their distance, sorted gating, and modulating factors like personality traits, relationships, and so on, motives, um uh and chooses what to do based on that.

**6:40** · Uh And traditionally, we have intentionally had them choose randomly from the best interactions, not choose the best one.

**6:48** · Again, because we want them to be suboptimal. We want them to make mistakes.

**6:53** · Uh and that's really it. Um there's no machine learning, there's no behavior trees, there's no planning. Sims are really just hamsters with jobs.

### Selfevident dependencies

**7:03** · And the last thing that I want to talk about with the sort of that's core to the Sims is what I call self-evident dependencies. Um By grounding the game in sort of mundane, obvious, and often pedestrian near reality, uh players generally don't have to guess uh what to do or more importantly what the Sims should be doing.

**7:21** · So, if a Sim needs to pee, uh I know what to do. Obviously, I need to have them use the toilet. So, I need to buy them a toilet. To buy a toilet, I need money, so I need to get a job. And if I want to get a job, well, I'll go to the computer or a cell phone or depending on which version of the game, I might just drive down to the to the restaurant and ask if they need anybody to work Um And in general, same is true for the larger core loop of the game. Um and that fundamental understanding and ability to relate to and empathize with your Sims and their plight um underlies most of the storytelling in The Sims.

### Projection and assumption

**7:53** · All right, so let's let's get into some of the specific techniques that we use.

**7:55** · So this is um the way this is sort of structured is uh it kind of starts with things that are a little more Sims specific and then sort of works its way into things that uh uh could pretty much be used anywhere, I think.

**8:06** · So I generally group them into a few categories.

**8:08** · Um so the first I want to talk about is projection and assumption. Uh so all right, quick survey, show of hands. Uh just how many people have played any version of The Sims? 1 2 3 4. Ooh, well, okay, pretty much everybody. You make a game for 20 years, eventually everybody will play it.

**8:24** · Um uh the uh so one more one more survey. So uh uh since you've all played The Sims, how many people remember the first time their stove caught fire and somebody burned to death?

**8:33** · All right.

**8:35** · Hopefully two-thirds.

### My experience

**8:36** · Um so that's an example of something I call the snowflake con.

**8:40** · And I'll explain what I mean by that. Uh but first my my experience with that. So this is my son, Aiden. Um and a couple of years ago, uh he doesn't look like this now, but uh a couple of years ago uh when he did look like this, um I sat him down in front of Daddy's game um and so that I could watch how he played, see how he set goals and things like that cuz we use our kids as test subjects and that's okay cuz it's our job. Um and my job is about peeing, so it's okay. Um uh and he proceeded to go into Create a Sim and make my wife uh his mom and and myself.

**9:11** · She's not flattering, so I don't have a picture of that. Um and then he started playing. And then uh after about 20 minutes or so, Mom Mommy and Daddy got started to get hungry. So he decided to have Mom cook something on the stove. Um but because she had no cooking skill, she started a fire. Um so he scrambled around trying to figure out how to put it out. Um but since he didn't know the game at all, uh it was too late. Uh and Mommy writhed in pain and was engulfed in flames.

**9:36** · Uh and then Mommy was burned to a crisp.

**9:39** · Uh and the Grim Reaper showed up and he took her away and I'm sure that would have been funny if you weren't six. Um and uh and and he left left behind a tombstone that literally had a tooltip that said Mommy.

**9:52** · Uh so that's what he named her. Um and my son lost his Um so he's just balling and and uh so so his mom runs over to see what was wrong and I tell her that she had in fact just burned in a kitchen fire because she's a horrible cook, which I thought was hilarious and kind of accurate and uh uh but uh she turns on the parenting cuz she's mom and and she starts comforting him and she's telling him that's just a game.

**10:18** · It's not really Mommy and obviously nothing happened to Mommy. Mommy's standing right here. And my son, who's still wiping away tears, just says, "I know that, Mom. I just forgot to save my game."

**10:28** · Um and my wife was projecting herself just about those events onto uh onto the whole thing and how they would make someone feel. Um but onto my son, um uh I thought this was just a hilarious sitcom moment that meant that I'd done my job and this game was awesome. And uh and my son just was worried about losing progress.

**10:50** · So ever since the original Sims, the game has been tuned to pretty much ensure that very early in the first game, um as evidenced by this the the hands, players will feel compelled to attempt to cook something. Um they won't have the skill when they do. Um and the stove will probably catch fire and cuz your first fire is just a crazy chaotic moment uh that you don't have any idea how to deal with. Um someone inevitably dies. Uh it's not scripted at all. Uh it's but it's encouraged uh through tuning.

**11:16** · Um a fire doesn't always start and when it does, it doesn't always damage the you know, it doesn't always do much damage or kill anyone. Um and when it does kill someone, it's obviously not predetermined who that is. Um in fact, there might not even be another Sim there to witness it. Um Uh but honestly, desperately attempting to cook a grilled cheese in the middle of the night to uh you're starving to death and then dying anyway alone in your kitchen because of a fire that you started cuz you suck at cooking um is not a bad story.

**11:44** · And we didn't write it. You did.

### Con

**11:48** · So, the reason I call it the snowflake con uh it well, the con part is should be obvious. Uh, people generally think that it is their own story and and technically it happens to most people.

**11:58** · Um, but everyone wants to feel special like a unique snowflake. Um, and giving them enough control over the specifics of their story scratches that itch and pulls them into that story in a really really special way.

**12:10** · That same story happens to almost everyone eventually. Uh, but each story is just different enough and each person's perception uh of what happened and how they felt makes it unique and special um and personal enough to be worth sharing. Um, for my son it wasn't just anybody, it was mommy burning and it was daddy failing to put out the fire.

**12:30** · So, he's probably still got that rattling around in here somewhere.

### Ambiguity

**12:35** · So, another projection trick that we use all the time is ambiguity. Uh, in The Sims we use players innate propensity uh to project to our advantage kind of pretty much everywhere. And to that end we're often intentionally vague uh when communicating with the player, particularly when explaining The Sims motivations. Um, we always try to leave the room uh leave the player room to project uh their assumptions and preconceptions onto their Sims. Um, and sometimes that's really hard to do as a designer.

**13:00** · The we often achieve that, like I said I've as I mentioned before, by communicating to the player in a manner that forces them to interpret the information subjectively rather than objectively. Um, there's just not enough there for them to to objectively evaluate it. Um, and we generally do that by being very vague or offering incomplete information.

**13:17** · So, one of the oldest and most obvious examples of this um are thought and speech balloons. Like The Sims communicate almost entirely with these.

**13:23** · Um, so there's uh uh they aren't always random. Um, they actually sometimes have in have intent.

**13:28** · Um, but they clearly leave plenty of room to project. Um, and there are thousands of these, uh, in the game.

**13:36** · Plus urine, because I keep my promises.

### Simlish

**13:41** · Uh, but another richer example is, uh, spoken language, which again, everybody's familiar with The Sims, so you've heard this, but uh, quickly, The Sims is, uh, they speak in their own language called Simlish, um, and it's this wonderfully ambiguous and vague, uh, mechanism. Um, and there's it's as a reason that we have never even attempted to put real language on The Sims, because this this idea of Simlish is so powerful and so, uh, from a uh, from a player projection standpoint. It sets a tone for an interaction, it leaves a ton of room for the player to project onto what's happening and to make it their own.

**14:10** · And if we use actual language, the game would flatten and shrink, uh, and everyone would be having the same experience.

**14:17** · Uh, and the that ambiguity also tends to make The Sims feel smarter than they actually are. And it can hide actually hide cases where we're doing something wrong, um, because you really can't tell how wrong it is, because you can't tell exactly what they're saying. Um, so if a Sim had an argument and he was reciting an exact specific argument, well, one, you'd hear the repetition, um, but we also run the risk, um, of going against the player's story. Like, the player may think this argument is about one thing, and then we make it so clear that it's about something else, um, and the player, you know, the the player feels this dissonance and it messes up their story.

**14:47** · So, a couple of really quick examples.

**14:49** · Um, so the first one is the end of an argument.

**14:56** · Um, you don't know what the argument's about, you know, she's pissed. Um, uh, that is someone mourning at a funeral.

**15:06** · But it obviously could be someone being sad in any context. Um, you can project onto that whatever you want. Oh, the uh, and and, uh, uh, and that is sex that didn't go well.

**15:24** · Ooh.

**15:25** · What's so famba?

**15:29** · So, one last quick note on ambiguity, something that should be obvious but that we discovered over time is that wrong is almost always worse than saying nothing.

**15:37** · Um so, as designers we have this natural tendency uh to want to tell the player everything. Um just we want to make sure that you're getting all of our genius and you don't miss any of it. Um uh but if we explain something that the player had already projected their own narrative onto, similarly to my example of using natural uh real English or real language, if we do that and we get it wrong, then the player's story collapses um and the magic just disappears.

**16:01** · So, I have a couple of images here. I don't have a heading for them. Um but they're really an abject lesson in how player projection can sometimes go too far or be a problem. Um this was a series of experiments. We didn't ship these, you'll see why. Um uh that we tested uh where we were trying to make certain Sims We're trying to give them more personality and we wanted to make certain Sims seem really rude or inappropriate.

**16:25** · So, I don't know if you can see it from back there cuz it's very tiny. Um uh that for all of these images, there is actually nothing going on in these in these animations. Um so, in this case, we wanted to make it look like she was making an obscene hand gesture. So, we put a what we call a sensor grid over her hand. And just the sensor grid, this animation has stayed in the game, but putting a sensor grid over it put it across the line with our players.

**16:47** · Um or way over the line in this case. Um so, the animation itself almost made it in because it was just kind of cheeky and silly um and there's nothing going on.

**16:57** · But you put a sensor grid on it and mhm uh and nope.

**17:04** · That's not happening. We were trying to actually put the sensor grid over his hands because we were trying to say he was typing something angry um and that clearly is not what anybody projected onto this.

### Randomness Urinals

**17:16** · And the last example of how powerful projection can be that I want to talk about is randomness. Um and urinals. I I warned you guys. Um because in The Sims urinals are really exciting.

**17:27** · Uh so, I assume everybody uh knows how urinal selection logic works. So, when you're going to the restroom and you're trying to choose what urinal to stand at if you're a dude, um you're basically uh doing a very very private uh thing in a completely inappropriately public space.

**17:43** · So, your goal is to be as far away from any other human being as possible. Um and if you're the first dude, you stand in a place that allows the second dude to be as far away from you as possible.

**17:51** · Um and so on. It's a little binary search and everybody knows where the next two guys are going to stand.

**17:55** · So, when we added urinals to The Sims, we we wanted to get this logic in there cuz we thought it would be funny.

**18:02** · Um but that's actually really really difficult to do in The Sims because the objects in The Sims don't know anything about each other and they don't actually know where they are in the world. So, if you line up a bunch of urinals, they all exist in their own little bubble and they don't know anything about the other urinals.

**18:15** · But one of our gameplay engineers actually got this to work. Um and I was really excited about it. Um and I don't I still don't know how he did it. Um and but he got it to work and we were really fascinated. So, we play tested it.

**18:24** · Uh and uh and people acknowledged that, "Hey, The Sims are doing it right." Um but it wasn't terribly funny. Um and everybody had the same experience and it wasn't a story that anybody was going to tell.

**18:37** · So, in the end, we took it all out and we went with something way simpler, random.

**18:42** · Because randomly this happens and that guy's a jerk.

**18:46** · And it's a story. Or this happens and I don't know what's going on there, but and I don't know who went there first, but it doesn't matter. Either way, it's weird and I would talk about it.

**18:56** · And that that guy in the middle is really confused and terrified.

**19:03** · And that's funny, too. I don't even really don't know what's going on there, but um uh that looks like desperation somehow to me. Um the but pretty much everything is funny in this context uh based on your sense of etiquette and your social contract and sense of humor. And in the end, we just put random thought balloons on it, too, cuz almost anything is funny in that context.

**19:27** · This might not have been random. And now because The Sims is fundamentally a sandbox, we generally try really hard not to tell the player what to do or to lay out specific paths or stories for them to follow. So, on the positive side, that allows the player a ton of flexibility and it makes the game feel really wide and it supports nearly nearly infinite replayability. On the downside for us as developers, that means a lot of classic design patterns or related to goal structure or storytelling are kind of off-limits for us.

**19:58** · Now, we know that the best game stories are collaborations between the player and the game where the player has enough agency to feel like the story belongs to them.

**20:07** · So, one of the places that we look for inspiration is improvisational comedy.

**20:11** · In particular, the concept of yes and. I assume most of you are at least somewhat familiar with improv, but just in case anyone isn't, I'll I'll explain real quick. The phrase yes and refers to a basic philosophy in improv by which a participant accepts what their partner has just said, the yes, and then follows on from that line of thinking, adding to it, the end.

**20:31** · For example, if I say, "Wow, it's cold in here." you might acknowledge that it's cold, smile all flirty-like and say something like, "Luckily, I have you to keep me warm."

**20:40** · And then I might acknowledge your suggestion that we cuddle to keep warm and respond with, "I thought we agreed we wouldn't do that now that our divorce is final."

**20:48** · You're right, you're right. What would Brian think?

**20:50** · So, now we know that we're freezing, we're somewhat amicably divorced, and apparently one of us is dating Brian, and he's jealous.

**20:57** · And we have a story.

**20:59** · There are several ways that we employ those philosophies in The Sims.

### Autonomous Feedback Loop

**21:02** · So, one of the longest-lived examples of yes and in The Sims um, I'm sure everybody's familiar with if you played it is um, but what I I call them autonomous feedback loops.

**21:12** · And there are a lot of them, but one of the clearest examples is the relationship system.

**21:15** · Uh, relationships uh, between Sims are represented as a value from -100 to 100.

**21:20** · Um, I hate you, I like you.

**21:22** · We've added some complexity to them over the years, but fundamentally they're still this.

**21:26** · And as players perform various interactions, various directed social interactions between the Sims, that matrix of relationships change.

**21:34** · Uh, the Sims grow to love or hate each other, get married, become enemies, and so on. However, the big A small I that I mentioned, um, uh, behavioral systems uh, that the Sims modulate the scoring um, of subsequent autonomous social interactions that they perform on their own um, using their current relationship state. So, the result is that the interactions that the Sims choose to do on their own inherently reflect what the player has previously directed them to do. But, uh, but there are a bunch of other factors involved, you can't really predict exactly what a pair of Sims are going to do.

**22:02** · Um, but if you've made them fall in love, they will do romantic, loving things. If you've made them hate each other, they'll pick fight with fights with each other. It feels like they are following your lead. Yes, and and they they maintain the the consistency of the story that the player is telling.

### suggestive control

**22:19** · So, another small example, um, is something I call suggestive control, um, cuz I think it sounds naughty, but it's not really naughty. Uh, the it's really just uh, giving the player the opportunity to suggest a vague intent to their Sim, um, and letting the Sim decide on the details. So, uh, the silliest example, simplest example is if I click on a bookcase and I ask my Sim to read, I get a picker that pops up allowing you to choose a specific book. Um, like I could pick how to seriously injure someone with this book. Um, and my Sim will read that book. Um, so, just like any other interaction.

**22:50** · But, if instead I tell them to read something, um, what happens is that the Sim goes to the bookcase, and then he looks at all the books that are in the bookcase, and then he scores them all big A small I style based on his personality and skills and careers and relationships and everything else, and they choose the book that they want to read. Um and it gives me a way to tease a little bit of the soul out of the Sim, um but I still am telling them what I want them to do.

**23:14** · Um so it's very literally almost yes and I want you to read a book and I'm going to read this book.

### gender preference

**23:23** · So one last example of autonomous feedback loops um is one of my favorites.

**23:27** · Um the uh this is not me, although it could be. Um the uh it's it's very simple and it's elegant and it's subversively progressive and I love it. Um and that involves the Sims concept of gender preference, uh which is our geeky way of putting it. The Sims come into the world having no sexual preference, um but when the player directs their Sim to initiate a romantic interaction with another Sim, flirting, kissing, whatever, the game tracks the gender of that target Sim. Now normally Sims will not perform any autonomous romantic interactions on their own.

**23:56** · Uh most people don't notice that, but they don't. Um but once you have initiated enough of romantic interactions um with a particular gender, the Sim will begin to autonomously romantically interact with Sims of that gender on their own. Um yes and um and we actually track the preference independently for each gender um and it's not a binary thing, it's a it's a continuum, so there's a lot of flexibility in there.

**24:20** · Um one interesting case we had here with this is um there was a this has happened more than once, um but one in particular where a congressman um made a stink about the Sims being sinful or corrupting our youths. Um uh seems silly in hindsight, but um and he knew that that was true uh because he had tried the game and the Sims were doing all sorts of debaucherous things.

**24:41** · Um and of course we as developers knew that that was only happening because he had done those debaucherous things over and over again.

### once

**24:52** · So uh the last example of yes and design that I want to discuss um are wants and fears and uh wishes. Uh and I'm going to go into this in quite a bit of detail cuz I think this is this is something that can be used in a lot of contexts.

**25:02** · It's definitely not Sim-specific. My examples will be Sim-specific, so uh try to generalize them in your head.

**25:08** · But basically, this was a mechanism that was it was initially introduced in The Sims 2 um as a lightweight adaptive goal mechanism. I'll explain what I mean in a minute. Um rather than a traditional prescriptive goal mechanism like quests, uh which as I mentioned, because it's a sandbox, we try not to do anything like that.

**25:25** · Now, essentially, the idea is that Sims have things that they want and things that they're afraid of. And when a Sim experiences something or performs an action in the game, either he does it or you do it, um they can have a subsequent desire to do something in particular, a want, that follows from what they just did. Now, how strongly that want uh how strongly they want it uh is based on various factors. Um this You're going to see a trend here. Based like their mood, their personality, their skills, their relationships, so on. Um and in this case, how recently the previous event took place. Uh to give it a concept uh a bit of temporal coherence.

**25:55** · Um the designers can author these dependency trees um or stories in a custom tool tool. I'll show you a bit of that in a second. Uh and they're constructed out of content that's already in the game.

**26:07** · Actions, states, state of state changes, and so on. So, there's no content added for this. So, if anybody's not familiar with it, this was the original incarnation of it just to show you the information that the player actually sees. So, this is just the top are four wants that the player has, and the bottom are three fears.

**26:21** · Um the player what the player sees is, you know, he wants to throw a party, he wants to become friends with this woman, um or he's afraid of this woman dying.

**26:28** · That's a little morbid, but fine. Um uh he's afraid of his party going badly.

**26:33** · Um as I mentioned, the designers can author these trees.

**26:36** · So, let's take a look at little Timmy here.

**26:39** · So, uh in our tool, um uh each node represents a possible action or desire. Um nodes with dashed outlines like this will never be shown to the player um as an explicit desire, um but if they're satisfied, they will enable subsequent things. So, they're like a a hidden hidden trigger almost.

**26:55** · Um, so let's say Timmy um, let's say player the player has Timmy stargaze.

**26:58** · Now, again, Timmy's not asking to stargaze, but let's say the player has him do it. Stargazing in The Sims is an interaction where the Sim lies on the ground outdoors at night and just kind of gazes at the night sky.

**27:07** · Um, but let's say he has him stargaze.

**27:10** · Now, all of a sudden Timmy wants a telescope.

**27:13** · So, you buy him one.

**27:15** · Uh, now Timmy wants to use the telescope.

**27:17** · Um, so I direct him to do just that.

**27:20** · And maybe now Timmy's inspired and he wants to discover a planet.

**27:24** · And maybe he's afraid of his telescope breaking cuz he's kind of grateful that you bought him one. They're really expensive.

**27:29** · Um, and if he eventually discovers a planet, which happens by by repeatedly scanning the night sky with his shiny new telescope, maybe he wants to join the science career.

**27:36** · So, you do that for him.

**27:38** · Now, he wants to buy a chess table, build logic skill, get promoted. Um, and he's still obsessed with that telescope breaking. It's really important to him cuz he's had it since he was a kid.

**27:46** · Um, and then when little Timmy finally does get promoted a couple of times, he decides he wants to be an astronaut.

**27:51** · Now, that's a story, but the game didn't force you down that path at all. And you chose to have Tommy stargaze one night when he was young. He asked for a telescope, which is cute, but you didn't have to buy it for him. But, because you did, he had a dream to discover a new planet and to become an astronaut.

**28:06** · Timmy wanted those things and you made it happen for him. You told that story step-by-step.

**28:11** · Um, but if you had decided not to buy that telescope, um, cuz you didn't have the money or maybe you never stargazed at all, uh, none of that would have happened.

**28:20** · Um, and and to be honest, you would never even know that Tommy had this latent desire to be an astronaut. It just wouldn't you just would have never found out.

**28:30** · So, that's it's pretty powerful. Um, but the very yes and nature of it meant that it's difficult to surface long-term goals. Um, cuz basically it's a it's just little little short-term things that come after uh, after something else happens. So, we gave the player the ability to promise to make promises to their Sims.

**28:47** · So, that allows us to do things like here you can see um as soon as he wants to discover a planet um we can have him say, you know, I really want to be an astronaut someday. And that's way more powerful. Um but the problem is being an astronaut is a really long-term goal in The Sims. It's going to take you a couple hours to get there. So, if we surface that right away, this whole thing kind of stalls out. Um but what we allow is that now the player can promise when Timmy says, I want to be an astronaut, you can say, I promise I'm going to get you that. I'm going to do that for you. And then Timmy recognizes that you promised it even though you haven't done it yet.

**29:18** · And then it acts as if it was acts as if it was as if it was satisfied so that uh the subsequent uh desires can show up and Timmy can help you make him an astronaut. He can suggest the same things but in a different order. And it feels even more like a back and forth between the player and the Sim.

### promise trees

**29:39** · So, I want to go through a couple of examples. I don't know if everybody can see these from back there. Um but essentially uh uh these are different These are trees that are actually were actually in the game. So, this is a tree for a romance Sim um which is our ridiculous word for promiscuous Sim cuz we can't say promiscuous. So, this is a Sim who likes to get around. Um so, that starting node, the bold one there, um remember the dashed ones are things the player doesn't actually see. These are things that we're tracking in the background and if they happen to happen, subsequent things will arise. So, in this case, if you have him make out with a new Sim, um he's going to want to woohoo in a hot tub. Woohoo is, if you don't know, is uh Sim for sex.

**30:10** · Um so, he's going to want to have sex in a hot tub, have sex in bed, and he's going to want to meet somebody new cuz he's promiscuous. Um and then he's not asking, but if you have him have sex with a second Sim, and then you have him have sex with a third Sim um he recognizes that you're playing him as promiscuous.

**30:28** · Um and then he says, I want to break up with my spouse if he has one. Um and he wants to have sex in public uh and he's afraid of being rejected for having sex in public.

**30:35** · Um and if you for some reason you you roll with this and you do have him woohoo in public, um then he wants to do it three times.

**30:43** · Um, the uh These are These aren't even trees, um, but this is basically an example, um, of a uh uh of a Sim with commitment issues. If you have him marry someone, he immediately wants to meet someone new.

**30:56** · Um, here's a Sim who's just, I don't know, dark, sad. Um, if you have them fall in love with the new with the Sim, they're afraid they're going to die.

**31:03** · The The that Sim is going to die. Um, and I kind of another sad example, this is somebody who wants kids so badly if the social worker takes away their child, uh they immediately just want to have another kid.

**31:13** · Which shouldn't be legal, but it's it's the Sims. Um, and those are very simple, but they can get crazy. These are trees that are actually a lot more like this than like those little ones. Um, and they can have kind of any structure.

### how they work

**31:26** · So, I want to go into a bit of more detail on how this all works cuz I think it's very important. Um, so on the surface, these feel like quest chains, um, but there's several significant differences, um, that make them make them kind of special special. So, first of all, uh the players have no knowledge of these trees. So, they're never presented in the UI, um, and players never explicitly uh choose to follow them. Um, it's nothing like that. In fact, even the Sims themselves do not technically realize they're on any of these trees because they're not, and I'll explain in more detail. Um, all the possible stories are evaluated in parallel.

**31:56** · Um, and in the case in in these examples, we're part of hundreds of trees that were authored, um, by the team, um, with tens of thousands of nodes in them. Um, but each tree is manageable, um, but they're all evaluated in parallel.

**32:10** · And everything that the Sim experiences, events, actions, what have you, satisfies every copy of of the associated node in every tree in the game. Um, and remember, there's no concept of being on a tree. The trees are just sequences of events and actions to be pattern matched against.

**32:25** · Um, and then every subsequent next node that follows from a completed node, uh is scored and considered simultaneously as a potential desire or goal to be surfaced to the player.

**32:35** · So, let's look at a an abstract example. So, here are several possible story trees. Um, these are these are just like the trees that we looked at before. Um, they're you know, they could have anything in them. Maybe a couple of them are romance-oriented trees. A couple of them are family-oriented. It doesn't matter.

**32:48** · Um, and let's imagine that each of these trees has a meet someone new node at the start of it.

**32:56** · Now, as I mentioned, um, as a Sim experiences events and actions, nodes are satisfied starting at the root.

**33:02** · So, when a Sim meets someone new, like say Sarah in this case, uh, every node that says meet someone new that is available, uh, in every tree, in any tree, um, is satisfied. And that enables these downstream nodes in every possible tree to be surfaced and subsequent as subsequent desires to the Sims.

**33:20** · Now, every subs- every possible next, all those gray nodes, are scored and ranked, um, back to that pattern, big A, small I style, against their personality, relationship, relationships, and so on, um, in a big pile. And the highest-scoring, most relevant desires, um, are represented as the Sims' wants or wishes or desires.

**33:38** · Um, and it does not matter what tree they're in. Um, uh, one thing that we did discover early on, um, hop back a sec. One thing that we did discover early on was that, uh, that temporal tuning, like I mentioned, like these nodes are part of the scoring, it's also how long it's been since that previous node was satisfied.

**33:57** · Basically, the scores decay the longer it's been. Um, we realized that we needed to score those or needed to tune those based on, uh, the player's memory and not our expectations in the real world, um, or even our expectations in our simulated world. So, for example, if a Sim's spouse dies, um, we might surface that desire for a week of game time. Even that seems short, but let's say a week of game time because their spouse just died. That's crazy. It should That's a story. He should worry about it. He should be mourning or maybe even having a fear of falling in love again. Um, but the player moves on way, way faster than that, right?

**34:29** · My Sure, my wife died yesterday, but that was yesterday. Today I want a hot tub and I want to get laid.

**34:36** · Um so uh So then, um like I said, this is actually it's right. This is just an example of that tuning. So you can see here a little bit of how we balance the various factors.

**34:51** · Now maybe a couple of those stories actually have flirty introduction up next.

**34:56** · So then when that happens, those trees advance and new gray nodes are uh are opened up. Um and they're all thrown, like I said, into a big stew and they're all evaluated against each other and the highest scoring nodes are surfaced.

**35:08** · And so on.

**35:10** · And so on.

**35:12** · And all of the gray next and all possible stories are evaluated. And that could mean that the Sim is hopping from story to story. Um but really they're just organically choosing whatever desires make the most sense on the given the totality of that Sim's experience at any given moment. And because of that temporal connectivity, whatever the Sims want will organically make sense to the player and will build the story. So a player could happen to accidentally wander very clearly down one tree behind the scenes. They won't know that. They're just going to think everything makes sense and there's that's yes and yes and yes and.

**35:42** · Um or they could end up hopping to another tree unwittingly um because the and made more sense than the and in the tree that they maybe were following behind the scenes.

### story progression

**35:59** · So the next big area that I want to get to um uh deals with something larger than that moment-to-moment uh that we've been going through. Um and that is that we also do uh sort of course chunky higher level simulations all over the place. Um often to make the larger world feel coherent. Um so traditionally in the Sims, your house or your lot has existed in isolation. Um you're in a bubble. Um your Sims lives go on, but outside your lot, um it's pretty much frozen.

**36:23** · Um now Sims 3 introduced uh the concept of a continuous seamless world um, and that introduced the problem for us in that we wanted the entire world to feel alive and everybody to be doing things, but we couldn't simulate 100 or 200 Sims. So, we needed another solution. Um, and what we arrived at was something we called story progression. Uh, and the basically uh, the Sims uh, that you can't see are running a really chunky simulation uh, that progresses their lives as you play.

**36:52** · The and uh, it allows us to do things um, like have the entire world grow up um, and maintain coherence. What we mean coherent in your story. So, you can have a childhood sweetheart uh, that our childhood friend who becomes your high school sweetheart. Um, you get married, you move in together, you have kids uh, and you can still go back and visit the grandparents in the house you grew up in and they will be in fact grandparents and not children.

**37:14** · Um, the the system again the same trend. The system is like a big macro version of the the big A small I behavior that I described. But rather than looking around the world for interactions on objects, um, the system looks at each Sim and scores possible life events that could happen to them.

**37:32** · Like get a job, be promoted, have a child, get married, things like that.

**37:37** · And we score all of those interactions based on various factors related to the Sim like their age and the standard personality and so on. Uh, and then we choose the best one.

**37:45** · Um, the one that makes most sense for that to be the next big life event for that Sim.

**37:51** · Uh, and we score all of those interactions based on uh, various factors related to or sorry, um, then we make the action true by changing the macro state of the Sim. And actually you've been a couple people talked about this already in other narrative talks or something similar.

**38:04** · Um, if we choose the Sim to be a policeman, um, uh, we skip the for formalities and we just make them a policeman. Uh, if we choose for them to get married, there's no ceremony. Um, it's way cheaper. Um, uh, we just make them now married uh, and so on. And the magic such as it is is that most of the local interactions that the Sims perform, uh like working out on a treadmill or reading books or making out or whatever, are all scored based on that Sim's state.

**38:30** · So, by manipulating the Sim's states directly in this big macro way, the actual interactions that they take when you are visiting them um or when you see them, will probably make sense.

**38:40** · So, if we made a Sim a musician, when you visit them, they'll probably be playing the piano or the guitar or whatever. Um and as they get promoted, um big chunky promotions that they didn't really earn um because life isn't fair if you're not looking. Um then we'll and we'll automatically bump his skill up to make it all coherent and make or consistent and make it make sense. So, when you come back a couple days later, your Sim has evolved and grown um and they'll be playing more sophisticated music, making fewer mistakes, and so on. Everything stays internally and contextually consistent.

**39:10** · Um and as an added bonus, uh we can alter the scoring of those life events globally uh to do sneaky things, like increase the chance of people moving in or increase the fertility rate um so babies are born faster um if the population has gotten too low. Um and at the opposite end of the spectrum, um if we have too many people in town, we can just start killing people off. Um or I guess in the most creepy way, if a player decides to have a baby um and the town is full, um then someone around town across town just quietly dies um to make room.

**39:40** · Um complete with a backstory, like the person who dies, they deserved it. They are the they they scored the highest on likely to die, so it's all okay. Um Uh so, what I want to show you here is actually a prototype um that we built.

### story progression prototype

**39:56** · Actually, the person who built it is sitting back there somewhere, Ray. Um They uh So, this is a prototype of uh of that uh story progression system, an abstract prototype. So, what you're looking at here is a town and every orange box is a house and every yellow rectangle is a Sim.

**40:13** · Uh and what you're seeing is them moving in.

**40:16** · Uh the lines are them forming relationships, falling in love, uh becoming enemies.

**40:21** · Uh and you'll see people again, they'll they'll get married, they'll move in together, they'll have kids, and we can zoom in here and look at one of them real quick.

**40:31** · This is Bubba and Mara and Madison. Bubba is all about popularity. He's outgoing and a good cook and a good kisser. He's a catch.

**40:38** · Well, he's a grocer, but that'll have to do. And then Mara, she's also about popularity. She hates the outdoors.

**40:43** · She's always late.

**40:45** · And she's a waiter.

**40:46** · And that's their daughter Madison. She will be a romance Sim. Um she's a fast reader and a horrible cook, so she didn't get that from dad.

**40:54** · Now, what's going on here? Uh this is Bubba's life story. This is everything that's happened to Bubba Bubba while you weren't looking. Um and if we if we zoom in here a little bit and look more closely, um we can see all the things that happened to Bubba uh in this thing.

**41:08** · So, one of the first things that happened to Bubba is he met Mara. Uh so, that's great. Um and then he became friends with Mara pretty quickly.

**41:17** · Um and then he fell in love with Mara before she fell in love with him, but but she came along soon. And then uh Mara proposed to Bubba a few a little while later. And then after a lengthy 7-day engagement, they got married um after they moved in together, but no judging. And uh and then they had a daughter, Madison, um and then they had to move to a bigger house.

**41:39** · Um but this is all that's happening behind the scenes. Um they happen very infrequently. It's really really cheap.

**41:44** · We could do this for hundreds or maybe thousands of Sims. Um and what that means is that if you knew Bubba or you knew Mara, um you would eventually be you would see them together, and you would eventually be going to a different house, and then eventually they would have a daughter, um and it would just make sense.

### inverse autonomy

**42:10** · So, one uh one more example um of sort of meta what I call meta story telling telling is inverse autonomy and I'll explain what I mean by that.

**42:19** · While story progression ensures that the individual NPC Sims and families remain consistent over time, another system that I call inverse this system ensures that the world itself is appropriately populated by NPCs. So, essentially this system makes sure that when a player visits a public space like a restaurant or a gym, other Sims just happen to be there.

**42:37** · And moreover, it attempts to maintain narrative appropriateness. And what I mean by that is that specific Sims that are in a particular place like a gym or a restaurant are the Sims that the player would expect to be there based on the story they're telling and the things that have happened in their world so far. The game does this by scoring Sims in the world against their appropriateness for a given venue.

**42:57** · Very big A small I like but in reverse.

**43:00** · So, instead of the Sims looking for things to do, we look at the Sims and say this Sim would be the perfect Sim to be here at the gym. So, if I've made friends with a professional athlete, it'd be cool if he was at the gym. That will make total sense to me.

**43:12** · And if I've made if I've met someone who's a bookworm, it'd be great if they were at the library.

### N of M

**43:19** · And the last example of of that I want to get into um is a pattern that I call N of M, which is not a very clever name but you'll see what I mean by that. Um and it's really about creating interesting narrative opportunities by giving the player multiple ways to succeed. Um by giving the player options, they can choose to tell their story their own story of their unique path to success.

**43:42** · I do now ideally the success criteria are not simple discrete yes no checkboxes. Even things like bring me 10 apples is still a checkbox cuz I can't bring you eight apples and get half of the half credit. Um so, and that's these continue or these non-discrete goals are interesting because they allow the player a lot more flexibility and there's a lot more success space and more room for player agency in their story. So, this is a really simplistic abstract example, but let's say that I need 100 points to achieve a goal in the game.

**44:11** · Uh now, maybe there are three sub goals that each can be completed at any level between zero and 100.

**44:17** · So, the player could go all in on one um and ignore the others, which would satisfy the parent goal.

**44:22** · Um uh or they could go wide across all the sub goals, but not completely. They could just partially do all of them. Um and that would still count cuz it adds up to 100. Now, the best example, I apologize these images cuz they are a little fuzzy cuz they're very tiny normally. Um is the The Sims 3 career system. So, in this example, um you might start out in the in the culinary career as a kitchen scullion. Um and your only requirements for success are your cooking skill and the mood you're in when you go to work. So, you can decide to go all in on cooking skill and practice cooking all day and then uh and not worry about the mood you're in.

**44:56** · Maybe the cooking If you're practicing cooking all day, it takes so long you can't you don't have time to shower and you don't have time to sleep. So, you're you're falling asleep and you stink all day and whatever, but it doesn't matter cuz you're an amazing cook.

**45:06** · Um I think there's a reality show about that. Um Now, when you get promoted, we might add a metric, say your relationship with your boss. So, you could continue trying to be a an awesome cook, but that was a lot of work. Um so, you could decide to just also build a relationship with your boss. Uh and you could decide you're going to keep learning to cook because it's only fair. Um and you're going to be your boss's best friend. Or you could say screw that cooking thing. I'm going to date my boss and maybe I'm going to marry my boss so I don't have to worry about any of this crap anymore cuz I'm married to the boss.

**45:39** · And then maybe we add one more. Um and we give you the ability to uh to have relationships with your co-workers. Now, if you're married to the boss, maybe you don't care about this at all cuz you're already golden.

**45:50** · You have You don't have to work at all.

**45:51** · Um but if you weren't married to your boss, um then you could decide to throw a party every couple days for your co-workers and also not worry about any of that other stuff. Or you could casually socialize with the the co-workers you like and you could keep practicing your cooking skill.

### perturbing the strategic landscape

**46:07** · And then, to make it more interesting, we do something I have pretentious names for everything that that I call perturbing the strategic landscape.

**46:18** · The Basically, we wait for you, the player, to have a plan and to start executing on it, and then we change the rules cuz we're dicks. I mentioned that. Um In the career example, let's say you did choose to marry your boss and you let all the other metrics slide, then a couple of career ladders career levels up the ladder, we change who your boss is.

**46:39** · Now, we didn't do that because you married your boss, we were going to do that anyway, right? So, if you weren't married to your boss, that's just a that's just a footnote. Hey, I got a new boss, that's cool.

**46:48** · But, if you were married to your boss, now you're screwed. Like, you're married to I hope you were in love because that's all you got, and you have to scramble to figure out real quick, how am I going to get good at cooking or how am I going to, you know, throw a big party for my co-workers or or whatnot because you have to catch up. Now, we didn't write a story for you, but we set you up to experience one. It's your story and we just made it more likely that you'd tell a good one.

### summary

**47:13** · So, in summary, empathy is extremely powerful. I think everybody knows that, and relatability makes empathy much more possible. Um if players can relate to your world and your characters, even uncurated, possibly random, stories will resonate. Projection is extremely powerful, and your players want to find meaning in everything.

**47:36** · Again, even random, they're looking for patterns and they're looking for meaning. Take advantage of that and give them the benefit of the doubt and give them room.

**47:44** · Um Follow your players' lead. Like, your players are trying to tell a story.

**47:50** · So, let them show you where to take them.

**47:53** · Don't over simulate. It's a really common thing. Like, it sometimes you think that's the easiest thing cuz you already have some other simulation. Um but large-scale core simulation driving uh localized state and then that localized state um driving local simulation is a very very effective tool.

**48:09** · Uh give the player a little bit of choice in their success criteria or a lot if you can. Um because even a little bit of player agency in those success criteria can allow them to tell their own story while allowing you the developer to maintain control over the overall progression.

**48:23** · Um and don't be afraid to move the goal posts. I mean don't be don't be a jerk.

**48:27** · But uh the if you're not frustrating them, this can be an awesome way uh to create beats in a story um that otherwise would have stagnated.

### questions

**48:38** · Thank you very much.

**48:47** · Uh so I talk a lot, but I think I have a few minutes for questions.

**48:53** · Uh sorry.

**48:55** · Yes, so uh I have two questions about the uh uh story tree system that you just described.

**49:01** · Mhm.

**49:01** · Uh first thing is would you say that adding contents into The Sims is essentially adding new possible uh tree trees into the game? Would I say that?

**49:15** · Um adding new contents? Is that what you said? Sorry.

**49:18** · Uh new content in Oh, yes, yes. Um usually what we did is we did them in conjunction. It's basically we would be adding content in a in an expansion or you know in DLC. Uh and all of that content then we could add new trees or insert it into existing trees. Yeah, so it made it very very easy. Uh because I said we were adding that content anyway for players to exper- you play with. Um and being able to weave it into all new stories made it even more more valuable.

**49:42** · All right, thanks. And the second question is um it's possible for players to when they get more experienced, they sort of uh discovers these trees they exist and some of them will try to find out an optimal way to play.

**49:58** · Like they probably find the easiest job to make money and be financially free then go on to do whatever they want.

**50:05** · That I think it's somehow hurting the the the possibilities to create new stories. Do you somehow do do anything to prevent that from happening?

**50:14** · I guess there's two things hiding in there. One, no.

**50:16** · Mhm.

**50:17** · Um Sims is not inherently a challenge-based game or you know because it's not an MMO or something where you have you know accumulated value that that matters. There's very little EPing going on in the Sims. Um uh that we don't worry too much. The other thing is for the most part these these stories are really just suggesting things that you could already do. So um so even if you found a way to sort of find your way through the trees if you even could recognize that they were there.

**50:42** · Mhm.

**50:42** · Um it probably still wouldn't matter because it's not really giving you an advantage. It's just telling you a story.

**50:48** · Okay. Thanks a lot.

**50:49** · Sure.

### cheat

**50:51** · What was that?

**50:52** · Hi.

**50:52** · Hi.

**50:53** · Thanks for a great talk. I might have a silly question but I got to ask.

**50:57** · Well I spent hours and hours playing first versions of Sims and I was really honest and I tried to make a lot of money and I tried to you know purchase better bed because my Sim was always tired and blah blah blah.

**51:11** · But then my friend told me that there are these cheats you know that you can make more money.

**51:16** · Right.

**51:17** · So there was just a word and couple of exclamation marks and Rosebud, motherlode.

**51:22** · Yeah.

**51:23** · So I was just wondering was this also part of the design and storytelling to give player choice to make more money like just with one cheat?

**51:33** · Um it wasn't part of the storytelling per se but it is catering to people who tell different stories. Like some people use the Sims more like action figures.

**51:41** · Like it's less about the Sims it's less about emergent stories and it's more about what we call doll housing. Uh so we wanted to make sure that you could.

**51:47** · Um the reason it's a cheat and not just in the UI is because we didn't want that to be the normal. We didn't want you to accidentally play that way because you felt we you should. We just wanted you to be able to play that way if you really wanted to. So.

**52:00** · Thank you.

**52:01** · Sure.

### death

**52:04** · Over there?

**52:05** · Okay.

**52:06** · Hello, thank you for the great speech.

**52:09** · And a question from a die hard fan of Sims.

**52:12** · Everybody knows Sims love to love to die by any stupid means.

**52:18** · And you usually add extra type of death with every game operation event every add-on.

**52:25** · Could you please explain how do you come up with new death? And what is the design flow for new death for the Sims?

**52:33** · Oh. Thank you.

**52:34** · That's a good question.

**52:35** · We considered a pack that I don't think we're going to do because it was a little too narrow. We considered a pack that was called dangerous things and it was just going to be ways to die.

**52:45** · Um It was fun to talk through. Um There isn't really anything too structured about it. I mean I think the biggest thing is and the I think the thing that some designers have trouble with is they want to some designers will say they want to make you cry. Like in Cats and Dogs the pack that we shipped recently.

**53:01** · Some of the designers wanted the dog dying to be this really sad thing like where the dog literally goes around to all of the people in the family and says goodbye. And then you know it dies it just curls up and dies and and we're not this the life is already pretty sad. So, we don't need to make you sadder. We So, what the biggest thing is is it a death that we can make charming?

**53:24** · If it's not a death we can make charming in some way charming or warm or heartfelt then we don't do it.

**53:30** · Thank you.

**53:31** · Sure.

**53:34** · Hi.

**53:35** · So, I've played all of the Sims and they all change like a lot between each of the iterations and I'm curious like what the like process is from going, you know, like the first Sim all the way to the newest Sim cuz there's a lot of changes between all of those.

**53:58** · Um well, the first Sim was Will Wright makes game or make I don't know if he still does, but he the way he did make games is he made games that were fundamentally fascinating to him. Um so they actually tended to be pretty geeky cuz he's pretty geeky. Um so the first Sims was really a more of a psychological study originally. It turned out to be way more fun than that and way more well, that's fun for some people. But it's way more fun more way way bigger than that. Um I used to joke that with Sims 2 like our goal was don't screw it up.

**54:24** · Uh it's a little more colorful than that, but don't screw it up uh because we don't didn't know exactly why Sims 1 was successful. We just knew that it was crazy successful. So just don't mess it up. And then so with 2 we didn't make that many changes. We mostly it was what I call a more more more design or 3M design.

**54:40** · We mostly just took everything in Sims Sims 1 and we added more to it. Uh the wants and fears that I mentioned was the one big thing that we introduced there.

**54:46** · Um and then in Sims 3 it was slightly different uh because uh we hadn't screwed it up. Um so that we had a chance to screw it up. Uh so we basically went all the way back down to sort of the core motivations of players and the core systems and said what systems what were they trying to achieve and could we achieve more? Um and uh or if a system wasn't really didn't have any purpose in the end, um we got rid of it. Um Sims 4 was a little more complicated. It's it's development storied. It went through several different stages, but Cool. Thank you.

**55:14** · Sure.

### fear trees

**55:16** · Hi.

**55:17** · Uh you talked a lot about progression on the trees by successfully completing your wants. Uh are there any like trees that are based off of successfully completing your fears?

**55:28** · Uh yes, absolutely.

**55:30** · Um so uh I didn't show any of those, but yeah, there are things where basically your Sims your Sim will have either regret or they'll have uh more crippling fears like if something happens that they were afraid of.

**55:41** · Um there are things where they react to fears. The dumbest one is a little tree that if there's a so not deep but it works within the same system as if they have a house fire they'll want to buy a fire alarm.

**55:52** · Like we all do after the thing happens.

**55:56** · So there are little things like that.

**55:57** · But yeah, we definitely did that a lot.

**55:58** · Um one thing that that reminded me that I don't maybe didn't make clear that again these nodes can be satisfied even if they're not wants. So even if the player the Sim doesn't want them they're still satisfied. So anything that happens can trigger these things.

**56:11** · Thank you.

### studies on play styles

**56:13** · Have there been any studies on the way that that players play The Sims that you know of? So like what would you say is the percentage of people who will uh do like this is me and my friends and my family simulation and then there's the people zoos.

**56:32** · Um we're just now getting into more and we're starting to look at ways honestly to use machine learning to try to identify play styles that are maybe more subtle than because those are really hard to detect in raw data. So the Sims before Sims 4 we didn't have a whole lot of telemetry. In Sims 4 we have every interaction that every Sim in every game has ever performed ever and we still have them. So we can we have this crazy reef of data that we can mine to do things like that.

**56:59** · We haven't yet figured out the more subtle play styles like are you torturing your Sims or are you you know playing your family or celebrities or things like that. Um we definitely do studies to try to identify the core clusters for how players play. We used to think of them really simplistically as like builders, casters, people who just make characters. Um or gamers who are actually trying to play like a game and progress or progressors doll housers, people who are just telling stories and they weren't actually playing the simulation. Um over time it's gotten a little more subtle than that. So the way they are our clusters.

**57:32** · But we're just getting into what you're describing. I'm really excited about it.

**57:35** · Um we're actually we're actually doing a study right now that is focused around how people handle romance. So like are they are they romancing a bunch of Sims? Are they all playing, you know, nuclear families?

**57:46** · Like that kind of a thing. So that we can decide where to make the relationship system richer.

**57:50** · It seems like a really good psychological tool for science. So I had a The other one I want to do is trying to see if people play to the characters that they create. So if you make a Sim that's mean, do you play them mean? If you make a Sim that's flirty, do you play them flirty? Cuz we on the behavioral side we make them try to act flirty, but I'm going to really curious to see if players lean into whatever the Sim was that they made or if they try to play against the grain because that's also fun.

**58:15** · Thanks.

### are there any game mechanics introduced that didnt have the outcome you expected

**58:16** · Sure.

**58:17** · Hi, The Sims 1 and 2 consumed my childhood, so thank you.

**58:20** · And also I'm curious, are there any Don't introduce me to your parents.

**58:24** · Are there any game mechanics introduced that did not have the outcome you expected?

**58:28** · Mhm.

**58:30** · That's a really good question.

**58:33** · Oh, I'm trying to think.

**58:36** · There I'm absolutely certain there are.

**58:38** · Uh But I honestly don't know any right off the top of my head. Um but part of that is that a lot of the mechanics that we introduce Mhm. No, I really can't think of anything off the top of my head.

**58:51** · No, sorry.

**58:53** · Okay.

**58:53** · I was going to say a lot of the mechanics that we introduce um in and of themselves this is going to sound maybe pretentious but in and of dodgy but like in and of themselves we don't necessarily expect a specific outcome from one system. We expect um a lot of the times when we're designing systems we design them to be interesting to bounce off of each other. We just try to make sure that there's enough touch points between them that interesting stuff can happen. Um oh, I do have one and it was a subtle thing. Sorry, it was back in this whims and fears so maybe it's just a little cautionary tale. Um these whims and fears in the original version they're very thoughtfully presented.

**59:25** · Like if you if your Sims if you do it right, your Sims will they will sound like they're just paying attention. Oh my god, like they get something. They're deep. There's a lot going on in there. Um and somewhere along the line, uh what we did is every morning when the Sim wakes up, they roll new Wants and Fears. They re-evaluate.

**59:40** · Um and somewhere in there, uh we decided that the way we should do that so you didn't miss it was we should make them spin like slot machine wheels. Um which uh honestly made me really angry. But in the end. But uh I angry. But uh was because what the effect it had was the players then saw them and because they looked like slot machines, a lot of players assumed they were random. Uh which given that we put all this effort into the system that made them extra not random and very intentional, um was a little disappointing um that some players thought that they were random just because of the way we ended up treating them in the UI.

**1:00:12** · Thanks.

**1:00:14** · I uh I was curious uh with the Wants and Fears graphs, uh if you ever considered having that drive uh autonomous behavior. Um benefits and hindrances to that. And also just how many of these in general are there in the game?

**1:00:31** · Um well, there are hundreds of them uh in the game. Uh uh and they uh like I said, probably easily thousands of nodes. Um the tool is built to be able to manage lots of data and to tune lots of data really quickly. Like to tune things across hundreds of trees at the same time um if you need to. Um it's pretty manageable because each tree is made in isolation and you really don't have to think about the other trees when you make it. So you can be like, "Ooh, I had a good idea for a story." And you can just go "Boom." Um and you don't have to worry about what it's going to do. You have to keep the scoring a little consistent, otherwise certain threads can overtake other threads, but it's pretty loose um and it still works.

**1:01:04** · Um Sorry, what was your other question?

**1:01:07** · My other question was uh did you consider using not just for Wants and Fears?

**1:01:11** · you can come work for us if you want. Um No, that uh that is something that um I would like to do in the future. Um so uh absolutely considering it. Um it doesn't do that obviously, or not obviously, but it I didn't mention it cuz it doesn't do that Um in the in the previous examples.

**1:01:26** · Um but it absolutely is something that I think would carry this to the next level and it's very natural and very easy.

**1:01:31** · Right? If the Sim is saying he wants this thing, um we could do it both ways.

**1:01:34** · The things the things that he they're actively surfacing could easily modulate behavior. Just throw that into the big A small I. Right? Now he's just trying to do those things on his own. Uh and I could see that being cool if it was a gradient. Like some things he cares about a little, some things he's obsessed with, and you know it because he you can't you have to keep canceling it. Stop using the telescope. Um that kind of thing. Um but we could also do it with hidden stuff just to make it seem it would be more subtle and would make the Sims feel a little more intentional.

**1:01:58** · And maybe when you saw him, you know, trying to call this girl, um even if he wasn't asking for it and you saw him calling you'd be like, "Oh, that's right. He met her at the restaurant."

**1:02:07** · That makes total sense. So, yeah, I know I think it's a great idea.

**1:02:10** · Thanks.

**1:02:12** · Cool.

**1:02:13** · Thanks, everybody.