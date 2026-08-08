---
title: "Cultist Simulator: Designing an Experimental Game for Commercial Success"
source: https://www.youtube.com/watch?v=0pBvMIUk1nQ
author:
  - "[[GDC Festival of Gaming]]"
published: 2019-07-15
created: 2026-08-07
description: In this 2019 GDC talk, Weather Factory co-founder Alexis Kennedy discuss the challenges and the advantages of the decisions the Weather Factory team made developing Cultist Simulator, how they steered
tags:
  - clippings
modified: 2026-08-07T21:11:30+08:00
---
![](https://www.youtube.com/watch?v=0pBvMIUk1nQ)

> 中文翻译整理：[[密教模拟器 实验性游戏的商业化设计]]

In this 2019 GDC talk, Weather Factory co-founder Alexis Kennedy discuss the challenges and the advantages of the decisions the Weather Factory team made developing Cultist Simulator, how they steered a straight course, and what they'd do differently next time.  
  
Register for GDC: https://ubm.io/2yWXW38  
  
Join the GDC mailing list: http://www.gdconf.com/subscribe  
  
Follow GDC on Twitter: https://twitter.com/Official\_GDC  
  
GDC talks cover a range of developmental topics including game design, programming, audio, visual arts, business management, production, online games, and much more. We post a fresh GDC video every day. Subscribe to the channel to stay on top of regular updates, and check out GDC Vault for thousands of more in-depth talks from our archives.

## Transcript

**0:04** · Ladies, gentlemen, and those who are neither, welcome to the very last day of GDC.

**0:09** · Uh thank you for coming. Uh Swery is on next around the corner if you're not sure why you're here.

**0:14** · Uh Carol, the stagehand, demonstrated her death stare uh earlier to me, and I I don't recommend being on the receiving end of it, so please turn off your mobile devices now uh to be safe from that fate.

**0:27** · And I've been asked to remind you uh that at the end of this session, you should turn off your So, you should turn off You should fill in uh the evaluations that you should receive by email, which is the most interactive part of the talk. I'm Alexis Kennedy.

**0:42** · Uh I am the CEO of Weather Factory, which is super fancy considering there are exactly three of us at the moment.

**0:48** · Uh and 2/3 of Weather Factory is in this room. My co-founder Lottie is over there in the front row. Our head of PR and marketing is uh back in London uh doing uh PR and marketing. And I'm here to talk about making art while making bank.

**1:04** · Cultist Simulator uh is the game I'm mostly going to be talking about, but I'll touch on some other stuff, too. And the key point here is the rejected alternative title for this talk, which was this.

**1:17** · Hands up if you think art is important.

**1:21** · Hands up if you think food is important.

**1:25** · If you put your hand up both times, you're probably in the right room.

**1:29** · If you're making free alt games, purely experimental art for art's sake, then good on you. Uh you're doing the Lord's work, and I wish you well.

**1:40** · If you are making games purely as product, and you're not interested in doing anything creatively unusual, this talk is likely to be less useful.

**1:50** · What we try to do at Weather Factory is experimental narrative work, and experimental means a rocky road, but it also means some opportunities commercially as well as creatively that you don't get elsewhere.

**2:04** · This is my who I am slide.

**2:06** · 10 years ago, I founded Failbetter Games uh in London uh where uh I made Fallen London. I was creative director on Sunless Sea. We did a bunch of other stuff.

**2:17** · And after 7 years, I had built Failbetter into a machine that made Fallen London games, and continued to make Fallen London. They're still doing that to this day.

**2:27** · And for that reason, among others, uh I talked a lot about this in my uh GDC talk last year.

**2:33** · I decided to leave and stepped away uh and did a sort of rolling year uh learning as much as I could from working for a variety of other studios.

**2:44** · And one of the things I learned, uh although I worked with some really great people, and I'd do it again, is that I'm not not suited for AAA.

**2:52** · So, I founded Weather Factory with Lottie with a brief, as I said, of making experimental narrative games.

**2:59** · And Cultist Simulator, our debut game, uh we made it in 11 months. The budget was less than 200K USD.

**3:10** · It's done very good business, and it's been nominated for two BAFTAs. So, I'm speaking to you in the uh brief bright moment after we were nominated for the BAFTAs, before we inevitably lose them to Florence uh and and Outer Wilds, but you know.

**3:27** · Uh so, let me talk about what it means to make experimental games that are also commercial games.

### Modus operandi

**3:36** · Fallen London um was my first project.

**3:42** · And the idea behind Fallen London is unbelievably stupid. It is a content-heavy free-to-play browser game.

**3:47** · The whole point about free-to-play games is you want people to shell out repeatedly uh for reproducible things, so you skin the same hat in 90 different ways and sell the all the different gifts.

**3:59** · Fallen London uh There was a talk on this, I think, earlier this week.

**4:02** · Uh It has a tremendous appetite for content uh because content is is what fuels a lot of free-to-play purchases. That was a stupid idea, as was designing it for web rather than mobile devices, because in 2009, I didn't know anything about anything, and I didn't realize that mobile was going to be a thing.

**4:21** · It doesn't have a genre.

**4:23** · It's very hard to elevate a pitch Fallen London or describe it in a sentence.

**4:28** · Super grindy, sorry about that.

**4:31** · Uh and very divisive. People do tend to love it or hate it.

**4:36** · Uh This wasn't a design intention, uh but uh for a long time it was it looked like something that had been built by one and a half people in a back bedroom on zero budget.

**4:47** · Nevertheless, when I left Failbetter, uh it was making enough money to pay a team consistently.

**4:54** · Those aren't the kind of numbers that get Zingers excited, but for a zero-budget passion project, 7 years after launch is pretty good.

**5:02** · Sunless Sea, as any of you who've played it or watched a let's play will know, is the world's slowest RPG.

**5:12** · It didn't really have a traditional box plot.

**5:16** · It's also got permadeath.

**5:18** · It's not sensible to put permadeath in an RPG, uh but we did.

**5:26** · It's once again got no discernible genre. It's sort of an RPG, uh but I'm stretching the definition to say that, honestly.

**5:34** · And once again, it's very divisive.

**5:38** · And it did good numbers. Again, not good numbers if you're Notch, but very good numbers if you're six people uh in a small room in South London.

**5:48** · Cultist Simulator. So, the first two, just for clarity, were Failbetter Games, my last studio. Uh Cultist Simulator was Weather Factory's debut title.

**5:56** · And once again, it's very hard to describe in a sentence, but it's deliberately obscure. It's more like sort of a cult solitaire than anything else.

**6:05** · And not only is it deliberately obscure, it has no tutorial, uh which is a choice we made with some uh nervousness.

**6:16** · Make a deliberately obscure game with no tutorial.

**6:19** · Doesn't have any kind of genre.

**6:21** · Severely divisive.

**6:23** · And these are the numbers we're talking about. Very small budget, very good sales considering, especially what a tough market is out there.

**6:31** · And two BAFTA nominations. So, what it means to be experimental, I'm going to read this comment because I I I enjoy it.

**6:38** · The approach is great. The ideas are great, and the setting and world-building are interesting and refreshing. Why, thank you, random Reddit commenter. Reddit has a bad rep.

**6:47** · But as a game design student, if I would have handed this in at any point during the year, they would have failed me instantly.

**6:58** · This is key when you're talking about experimental stuff.

**7:01** · Doing things that no one else is doing, things that people wouldn't normally do, is an advantage, all else being equal.

**7:09** · It means creative innovation. It means commercial innovation, which in a market as tough as the one out there right now, uh is a big deal.

**7:19** · But, there's a catch.

**7:23** · Very often those things look stupid.

**7:25** · Worse, often there are good reasons you put a tutorial in a game, or from there are good reasons why what you were taught in your first year of game design are things you should do.

**7:35** · And this is the catch. Until you actually do the thing, it's very hard to work out what's stupid and what just looks stupid.

**7:43** · So, to try to narrow down the things that have worked in the more experimental stuff uh that I've done over the years, and the stuff that doesn't, I want to introduce you to my failures.

**7:54** · These are not all my failures. These are only some of my failures.

**7:58** · You won't even have heard of most of these, for very good reasons. I wasn't creative lead on all of these. Um uh but I signed off on every one of them, and I bear responsibility uh for their failure.

**8:11** · Uh Black Crown project was back when I thought that free-to-play uh uh narrative was going to be the way of the future to replace novels, because I was insane. Storynexus is the uh shared narrative platform, which was going to make us a lot of money, and instead nearly tanked Failbetter at the time.

**8:30** · So, I think probably I've had twice as many failures in my career as successes.

### What do the successes have in common?

**8:38** · Here are the things that I think the successes had that made them successes.

**8:43** · One is that they were both distinctive and divisive.

**8:47** · I'm going to talk about the difference between that in a bit, but both those things are important.

**8:51** · They were all reasonably good.

**8:53** · Sounds a bit like I'm being flippant when I say that, and um people differ on the quality of some of them, but none of them were actively dreadful.

**9:04** · All of them, very important.

**9:07** · Super small budget by the standards of game dev, and very short timelines. Cultist Simulator, 11 months. Sunless Sea, 16 months. Fallen London, from the time we wrote the first line of code to the time we launched in um public beta, was I think four months, although it's been worked on ever since.

**9:27** · And a suite of design techniques, to which I'm going to give the super fancy name of Apophylian Design, and I'll come back and talk about that in a minute.

**9:36** · So, why all these things? Why are they useful? Why are they important?

**9:41** · Particularly if you're an indie dev, it's vital to lean into your limitations.

**9:48** · All studios have limitations.

**9:50** · Indie studios are basically made of limitations.

**9:55** · I used this slide in my talk last year, but I love it, so you get to hear it again.

**9:59** · This is one of the characters, one of the primary characters from the popular documentary, science documentary, Aliens.

**10:09** · It's the M577 armored personnel carrier.

**10:12** · Uh and it's made of all kinds of fantastic science And it's basically indestructible and it's very expensive.

**10:20** · You probably remember that it doesn't make it all the way through the film.

**10:26** · This is Rebecca Jordan.

**10:28** · She's 9 years old. She has a second grade citizenship award.

**10:32** · And she has one very important limitation.

**10:35** · She's really small.

**10:38** · So, her lifespan is much greater than that of the M577.

**10:42** · And as an indie studio, you're not the APC, you're Newt.

**10:47** · So, find what your limitations are and lean into them. Some of those limitations are common to everybody who's reasonably described as indie.

**10:54** · Small budgets, limited resources.

**10:57** · Two talks on the wind physics of God of War uh this GDC and I'm sure both of them are excellent uh for specialized audiences, but I've never made a game with wind physics.

**11:08** · So, all our limitations are different, but they tend to overlap in similar places.

**11:13** · And that's what this talk is about.

### Distinctive

**11:16** · So, being distinctive and the problem with this slide is that giving you advice on how to be distinctive is of limited use.

**11:24** · Because if I tell you all what to do to be distinctive, assuming it's good advice to do it, assuming you go out and do that, congratulations, none of you are distinctive.

**11:36** · So, find what makes you distinctive, find your specific limitations and lean into them.

**11:41** · But because they give me a free pass for GDC and everything, I have to give some specific advice rather than talking happy generalities. So, let me give you a a couple of pieces of advice.

**11:52** · One is this.

**11:54** · So, this is the key art for Cultist that the insanely talented Katherine Unger did for us. It's it's uh it doesn't tell you anything about the experience of playing the game. Sorry, let me rephrase that. It doesn't tell you anything about what you actually do in the game. It does tell you something about the experience of playing the game.

**12:12** · It evokes some of the emotions and some of the setting details you're going to deal with. And once you've seen it, you tend to remember it.

**12:23** · Very very annoying thing, if you're a writer, as I primarily am, art is much more distinctive than text. A wall of text looks like a wall of text from a distance, uh but art immediately looks distinctive.

**12:37** · And lots of indie games, for this reason, use a distinctive art style or distinctive key art to stand out from everything else out there.

**12:49** · And here's a really important point. You don't have to spend a lot of money to find something distinctive. Again, leaning to your limitations. Sometimes you do, sometimes you can. Some games need to be beautiful and need to look like all the money that was spent on them.

**13:04** · But here is uh this is Winter, one of our uh Cultist acolytes. And Katherine Unger, in the little time she had at the beginning of the project, cuz we didn't have her for very long. She's she's uh quite reasonably very sought after, established this art style for our cards.

**13:22** · Uh this uh my co-founder tells me this is this is something sort of like vector art. I don't really know what that is, but it it sounds important. And the key things about this is about this art. First of all, it's very distinctive. People use this art style now uh for Twitter avatars or Steam avatars to identify themselves as Cultist Simulator players. And everybody who's seen it knows it.

**13:44** · It's also really cheap to produce in mass quantities. You can whack out several of these in a day quite easily, which when you have our budget is vitally important.

**13:54** · So, that's one good way of being distinctive. Here's another one, a much more general one.

**13:59** · Genre.

**14:01** · Genre is a tool for communication and a tool for marketing. If I say that I'm making a side-scrolling 2D RPG, you immediately know a lot of what I'm trying to do. And it's you immediately have some idea if you're likely to like it or not.

**14:15** · But so people will tell you that you should find a genre that you should um fit your game into the places where other people like those genres. Uh you should try to establish commonalities based on that.

**14:27** · And that all can be good advice.

**14:30** · But there is another route, and the other route is explicitly to eschew genre. And and even if you explicitly eschew genre, we'll still talk about Cultist Simulator being um sort of a simulation or sort of a a card game or sort of a roguelike or sort of a horror game or try to get to those audiences.

**14:46** · But if you identify yourself firmly with a genre, it's very hard to stand out from all the other things that are in that genre. So, eschewing genre is one way to be distinctive.

### Divisive

**14:58** · Divisiveness. Right, those of a nervous disposition may wish to look away now, because I'm going to show you some orange text.

**15:08** · It's not something that a dev ever wants to see. Cultist Simulator is actually wedged at 77% mostly positive on Steam and is unlikely ever to budge from there. It'll never make it into very positive, it won't sink into mixed. But every time we run a stay a sale, we get a rush of people um who haven't heard about the game through word of mouth, haven't been recommended by a friend, and many of them don't know what they're getting into and react with confusion, dismay, or anger. And that anger is reflected in a sinking into mixed.

**15:40** · This is what divisive means.

**15:43** · So, look at the number at the top there.

**15:44** · This is someone who's spent almost 60 hours.

**15:50** · I know, right?

**15:52** · Uh but they have actually a very long list of reasons they don't like the game. I I only uh showed you the top part of the review, but it's it's it's like 1,500 words. They feel very very strongly about it.

**16:04** · And reviews for Cultist Simulator tend to come in three varieties.

**16:11** · People really like the game.

**16:14** · People just bounce off the game.

**16:18** · Or people nearly like the game, but too many of the unusual design choices you made or the rough edges uh annoy them.

**16:24** · And you know, this this is the third.

**16:26** · Very divisive game. In a picture, why is divisive good?

**16:34** · How many of you see a blue dress?

**16:40** · How many of you see a white and gold dress?

**16:45** · The weird thing for me, I don't know if the the the background's changed it, but I used to see this as uh blue and black.

**16:51** · When I was putting the talk together, uh I saw it as blue and black. And and when I started backing the talk, I saw it as white and gold and now I can't flip back. So, for poorly understood reasons, this presents to about half the world as white and gold and about half the world as blue and black.

**17:04** · And the reason that many of you recognize this image is that it went viral because everybody who saw the dress as blue and black could not believe what the white and gold folks were on about and they wanted to explain to each other why they were wrong.

**17:20** · And if you are an indie dev trying to build a community, yes.

**17:27** · The thing about communities, and this leads into uh the dark arts, honestly, is that a community is defined by other people not being part of that community.

**17:37** · Any community that doesn't have an edge is the human race.

**17:42** · And um the thing about uh a community that has strongly defined boundaries is it feels very strongly about its identity.

**17:51** · Now, in the age of Brexit and Trump and the polarization of politics in the UK and the US and elsewhere, uh this this is going to evoke some alarming thoughts. So, you must only use this power for good. But the thing is, in the case of Cultist Simulator, in the case of games with thoughtful, non-toxic communities, often this power is usable for good. I said earlier that there are three kinds of response to Cultist usually.

**18:17** · Love it.

**18:19** · Don't get it.

**18:20** · Nearly love it, but hate it.

**18:23** · And very very often, I'll jump into the Steam forums, the Steam forums of all places, and I'll see a a thread that begins by somebody saying, "I don't get this game at all. It's it's it doesn't work I I put cards in slots and words happen."

**18:37** · And occasionally, uh it's a reasonable summation of the game, honestly. But occasionally, um people will will come in and go, "Lol, sucks to be you. This game is for smart people." But that doesn't often happen, fortunately. Uh what what very often happens, heartwarmingly so, is the thread will fill up with people saying, "Yeah, it's a tough one, this.

**18:58** · Where particularly you running into problems? Have you tried this? This is how you fix the problem you're talking about. Read everything really carefully.

**19:06** · No, seriously, read everything really carefully. It all means something."

**19:10** · So, if you have a divisive game, then your community has very strong boundaries. Your community will feel very strongly about being part of the community. Your community will often want to uh to recruit other people.

**19:25** · Right, make your reasonably good game.

### Advice...

**19:29** · This is the most important advice I can give you.

**19:39** · And we're done.

**19:41** · No. Uh So, we're talking about making games which are creatively and commercially successful.

**19:54** · If you go far into the art end of things, a lot of conventional metrics for what is good, is it fun, does it sell, does it attract review scores, are of limited use. But where we are, on the boundary between the two, you can't say that too loudly.

**20:14** · It has some effectiveness if you are doing something creatively interesting and unusual, then people will give you a lot of leeway.

**20:23** · But um but only so much leeway.

**20:29** · Your game still has to be good.

**20:32** · So uh again, this is this is a pretty general piece of advice. So let me talk specifically about a way to make your game better if you're making a experimental game.

**20:45** · Feedback is vital.

**20:49** · Feedback from the community is the lifeblood of games. I've I've of indie games day. I've gone to like five talks this week where people have said, absolutely correctly, that feedback from the community is what can make a a good game into a great one.

**21:04** · Or an incomprehensible one into a decent one.

**21:07** · But you can design your game in a way that makes it easier for people to give you feedback.

### Being a feedback sponge

**21:13** · For example, Cultist the the core loop is you put uh cards into slots, and then words happen. And then you you you combine the build other cards, you have outcomes, they produce more cards, there's a virtuous cycle of more cards giving you more combinations and experimenting with those and finding more things.

**21:35** · And that core loop was available from the moment I had working code, even when it it looked really shonky. In fact, the core loop was available before I had a beta or an alpha.

**21:47** · Uh I put a prototype doing uh with with a crappy JavaScript gray box interface on the web for free, and just said to my existing community folks, "Here's something that I think might have something going on. I think it might be interesting. Do you want to have a a look at it?" People looked at it, people gave feedback. So before even the game had an alpha, I was testing the core feedback loop and seeing whether there was something uh there.

**22:16** · You've been to a bunch of talks this week already, I should think, that the emphasize the importance there. So I won't really get into it, but talk to your community, get all the help you can from your community, learn from them.

**22:28** · Particularly, educate them. So there's two reasons that's important. If you educate your community about your design decisions, then they will give you better feedback, and they will educate other people to give better feedback. So for example, in Cultist Simulator, one of the things you start doing very early on is to drag your job card into your work slot, and it produces some money, and you do that over and over again.

**22:56** · Over and over again. So you see what I did there, right? I did an art. You have to drag the work uh card into the work slot over and over again.

**23:04** · So my community started um pointing out there was no automation for this. They have to do the same thing over and over again. I said, "Yeah, well, I'm doing an art. I want you to feel that it's tedious, so that when the opportunity comes to start studying forbidden magics, you're like, "Ah, this is the cool stuff."

**23:22** · And they said, "That's that's true, but also RSI."

**23:26** · So rather belatedly put in a a double-click option so you can send the card directly to the slot. I didn't want to to pull back all the way um on making it a deliberately repetitive unpleasant thing.

**23:37** · But if you educate your community about why you're doing things, rather than just saying, "It's my vision," then they can respond meaningfully about which bits are a problem where you need to fix them.

**23:49** · And here this is key. Cultist Simulator, when we were first discussing it, uh could have been more like an RPG than like a roguelike.

**23:59** · The loop of Cultist Simulator is you play it for basically an evening, maybe two, maybe an hour if things go badly, and you complete it. And then you try it again for a different goal, different set of start conditions, see which thing how how things shake out differently.

**24:13** · And there were several reasons we chose to do this, one of which is my continuing besotment with FTL, but one of them was that so that we didn't burn out our testers.

**24:25** · If you make a 60-hour game like Sunless Sea that you play through once, you need a steady stream of alpha and beta testers if you want to keep getting feedback from it. Nobody is going to keep playing the first 15 minutes of your game. The first 15 minutes are the most important.

**24:44** · But if you make a game where you have to to do constant runs, then you can keep on using the same community, the same community you spent all this time educating.

**24:54** · You can keep on getting meaningful feedback from them as you add features to the game.

**24:59** · So that's a couple of design choices there specifically intended to make the game more likely to attract feedback and to make it easy to manage feedback around it. They're all to do with the game design, not to do with the cool ops stuff like automated um feedback and heat tracking that I've seen in other talks this week.

**25:17** · That that stuff stands great as well, don't get me wrong, but this is a design talk.

**25:21** · Right.

**25:23** · So, I showed you a bunch of projects at the beginning that I've worked on. Three succeeded, more than six failed, seven, eight, I can't remember what it was.

**25:33** · The thing about experiments is they often fail.

**25:36** · If they didn't, they wouldn't be experiments, we wouldn't need to keep doing them.

**25:41** · So, ooh, every time I look at this I get chills.

**25:46** · Jake Birkett did a Twitter poll uh last year, and he asked uh people how long they've been working on their game. Now that's how long people have worked on their game, not how long did they take to finish their game. So more than half the people who responded, Twitter poll, it's not scientific, but you'll probably recognize these numbers, said they've spent more than a year on their games so far.

**26:12** · These are also Jake Birkett's numbers.

**26:14** · If a game makes $100,000 on Steam, which isn't a hit, but most games aren't hit, and if one person has been making it for 1 year, then that's the hourly wage at the end of it.

**26:27** · If you have a team of more than one person, or if you are working on it for more than 1 year, those numbers get much worse very quickly.

**26:36** · So the thing about experiments is keep them cheap, keep them small.

**26:43** · Sure, there are lots of ways to manage your risk. You can get a publisher uh who's going to take a chance, harder and harder. Um and and they they they will not, but it's something you can do.

**26:52** · You can throw something out there in early access and then lean into it. A lot of the successful games I've heard about this week have been people who have an initial winning formula and then iterate and keep on providing free updates. All these things work.

**27:03** · But if you're doing experimental stuff, if you're trying things that you think genuinely may be stupid ideas, keep them cheap, keep them small, don't get lost in the vision.

**27:13** · And there's another advantage to that.

**27:16** · That advantage has to do with improving um how you spun wholesome anecdote that might even be true, I don't know.

**27:25** · It is said uh there was a pottery teacher who one term told half her class to make the best pot they could over the course of the term, and the other half the class to make as many pots as they could over the course of the term.

**27:43** · And after a term, half the class had all made each one really bad-ass pot.

**27:50** · The other half the class had made each of them a lot of bad-ass pots. As you keep on making pots, you get better at making pots. If you're polishing a pot endlessly, it's probably not going to be that much better.

**28:04** · And particularly with games, when the whole life cycle is different, you go through pre-production, you go through production, you launch it, you get feedback of a different kind of nature from press than you get um when it's in early access or beta.

**28:18** · You start it over again, you change your tools, you change your approaches. You learn things in a different way when you finish and launch a game. So finish and launch as many games as you can on short budgets, and that reduces your risk, and it means you learn more stuff.

**28:32** · Derek Yu has pointed out that finishing a game is a whole different skill set.

**28:38** · It's probably exaggeration. It's it's it's it's not the same skill set as making a game. Actually finishing it is hard.

**28:44** · It's very worthwhile to practice that.

**28:46** · Right, last section, but the longer section.

**28:50** · What is apophenia?

**28:53** · Many of you know, or you may do know.

**28:55** · Those of you who don't, this is apophenia.

**29:01** · Those don't look like faces until they look like faces, and then they don't look anything like anything except faces.

**29:10** · So apophenia is the human tendency to make patterns and to find meaning in gaps.

**29:16** · And if you're a game designer with a limited budget, apophenia is great.

### Apophenion design

**29:25** · So the three rules that I set for for apophenia design are one, don't simulate where you can imply.

**29:35** · Two, show your mechanics to your players, make your design visible.

**29:40** · And three, lean into your limitations again, cut, limit what you do.

**29:48** · We talk about each of those.

**29:53** · All digital games with some trivial exceptions run on computers. They're all software.

**30:00** · Computers are all good at simulating. Software is designed in large part for simulation.

**30:08** · So, simulation is always a temptation when you're making a game. You try to make the thing that you're modeling as much like the real world thing as possible. You think I'll just add more behavior to it. It'll be more sophisticated. It'll look more like the actual thing. We try to do photorealistic uh graphics or you have two separate talks on um on wind physics uh for your extremely gorgeous I love God of War. Don't get me wrong. I'm not dissing God of War. But, the point is that isn't available to most of us.

**30:35** · Simulation is very often a temptation.

**30:38** · So, for hundreds and in some case thousands of years other creative forms who can't simulate anywhere except between the player's ears, those art forms have been finding ways to use apophenia to leave gaps in the work that the player can insert their imagination into.

**30:57** · And if the player inserts or the or the viewer or the reader or or the listener or whatever, if player of your game inserts their imagination into a gap, two things happen. One, they feel that they own the experience.

**31:10** · It's more creative experience. And they're going to be more engaged with the game. Two, the CPU cost is a lot lower. You get a a lot more bang for your buck.

**31:20** · So, let me give you some specific examples.

**31:30** · What happened here?

**31:32** · If you played Cultist Simulator, uh you'll recognize this experience. If you haven't, what this player has done is they've completed a dream action in the game that has unexpectedly torn away the veil of the world and shown the Mansus, the place behind the skin of the world where the secret gods, the Hours, um rule.

**31:51** · Whoa.

**31:53** · Of course, in the game we haven't simulated that at all. What we've done is we've shown the uh animated graphic that indicates completion of a task. And then we've done a a rather nice transition. And then we've shown uh this uh big fancy evocative graphic at the end. We haven't shown an avatar lying down to sleep, putting the covers over, closing their eyes, and then a bubble comes out of their head, and then you see the Mansus in there, and the Mansus expands the world. So, there's a lot of gaps.

**32:18** · And filmmaking, uh the Kuleshov effect is this this idea of of long and venerable standing that if you show two visual elements in sequence, people tend to draw a line from one to the other. They'll make an assumption. If you show somebody and you show a coffin, then you the reasonable assumption is that somebody is in the coffin.

**32:39** · If you show a tabletop and then you show a dream world, then sometimes you can suggest that the character's gone in the dream world even though there's no character visible in the game.

**32:49** · That was just in here in case the animation didn't work. Top tip.

**32:52** · Uh textually, uh so writing is great for this. And text also is cheap because writers, God help us, are cheap as chips.

**33:04** · Uh Glover and Glover is the firm that you end up working at uh in uh Cultist for a chunk of the early game, potentially the whole game.

**33:13** · And we never specify what kind of firm Glover and Glover is. It's got clerks.

**33:18** · It's got desks. It's got windows. It's got management system. It pays people.

**33:24** · It's run by a family, but it might be an accountancy firm. Might be lawyers. It might be a shipping firm. Might be something else. We never talk about it.

**33:32** · But, everybody That's not true. Many of the people who play the game will have had um a soul-destroying office job at some point.

**33:41** · And they'll bring their own experience to Glover and Glover, and they'll make assumptions based on that.

**33:47** · So, use your players' experiences.

**33:50** · I just approved there as well. Uh the second uh line there gets quoted uh a lot. People like it. Um and curl my hands into the correct shapes.

**34:01** · Not with a little there. You you the hands aren't bent. They're curled.

**34:05** · There's muscular tension there.

**34:07** · Into the correct shapes. We've got a sentence that you you're conforming to something. And we also hint at the occult sense of correct shapes out there in the game. Comma and begin. Full stop.

**34:21** · Not and begin the day. The day proceeds.

**34:23** · It's very boring. And this happens. And I looked out of the window and I saw a ship. And all of that.

**34:28** · Uh as the adage has it, um uh getting late and leaving early. Leave the gap for the player to uh assume experience.

**34:38** · Well, here, I could have been unhappy.

**34:42** · I'm not unhappy.

**34:44** · That gets quoted a lot, too.

**34:48** · We don't tell the player So, this is this is a retirement ending.

**34:51** · This is one of the alternate endings in the game.

**34:53** · Um if you end up getting to sort of mid-level in the game, getting a promotion or two, and then you decide to retire, you get this rather melancholy ending.

**35:04** · It's not it's not a bad ending.

**35:06** · It's kind of a victory.

**35:08** · Uh And the key thing is we don't tell the player that. We let them bring their own experience to it. So, text is really good at leaving these spaces.

**35:16** · You know what else is?

**35:18** · Game design.

**35:21** · So, here is the core mechanic of Cultist Simulator. You put cards in slots.

**35:27** · You hit start, and something happens.

**35:30** · There are a limited number of slots in the board. Fun fact, there are usually about five, six So, there are a standard five, six verbs on the table.

**35:39** · And a uh verb cycle normally takes about 60 seconds, which means if you have all the verbs going at the same time, something happens about every 10 seconds, and you can see it coming, which is what makes the game addictive, which I stole from Civilization. Thank you very much, Sid Meier.

**35:56** · And um but you only got one work verb, one one explore verb, and one dream verb.

**36:03** · And the work verb is work in two senses.

**36:05** · It's work in the sense of go to Glover and Glover um and earn money. It's also work in the sense of the great work, the the magical work uh uh and so you can use two kinds of things in work. You can use your job cards and your abilities to generate money. And you can also use rights to perform occult operations and summon things or uh murder people or or or whatever you feel like doing.

**36:34** · The point is you can only do one of those at a time.

**36:38** · If you're doing occult operations, you are not going to work and earn any money, and vice versa.

**36:44** · Uh and this is the core of the one of the creative intentions of the game.

**36:50** · It's the division between your day job and the secret wonders of the night.

**36:55** · Which a lot of indie devs who've worked part-time on their own projects will recognize. And I and I I'm not even being um uh cheap there. I was When I first did the Cultist Simulator prototype, I was about to do a bunch of contract work, and I was uh creatively engaged by the the difference between the things you love doing and the things you you you have to do.

**37:15** · But, the point is Cultist doesn't give you a speech about that. There's no opening text crawl that says, "The choice that the human must make is between dreams and life."

**37:25** · It presents that mechanically uh for you to absorb and enthuse about on a Steam review, hopefully.

**37:33** · Here's another game that does something beautiful with mechanics, very minimally.

**37:37** · Um Heretic Operative came out last month.

**37:41** · Strongly recommend it. Um sort of uh Elder Sign: Omens uh board game-y sort of thing. Um the only two numbers you need to worry about here um that our NPC has are uh the one by the black cross, which is corruption, and the one by I think the orbiting two hands, which is tranquility.

**38:00** · And magic in Heretic Operative works like this.

**38:05** · You every time you cast a spell, you gain corruption.

**38:09** · Corruption reaches 100, you switch sides.

**38:12** · Every turn, whether you cast a spell or not, your corruption goes down by your tranquility. So, if you manage to spend some time not doing magic, then um you'll return to normal.

**38:24** · You don't spend magic points. You don't take health damage. It's just the corruption stat.

**38:29** · If your corruption crests 50, I think, you become curious.

**38:35** · And that means your tranquility drops.

**38:39** · If your corruption crests 75, your tranquility drops again, but you become open-minded.

**38:46** · And your tranquility can go negative.

**38:49** · What that means is your corruption will start rising every turn because you're just too open to the things you shouldn't be open to. That's lovely. That tells you a lot of the things you need to know about the way magic operates in the game. And it's also a really interesting mechanic. Lovely design.

**39:06** · But, that is apophenian mechanical design. That is using design to tell a story.

**39:12** · The problem with leaving gaps, of course, is that the player players don't always go where you want them to go. If you leave a gap, sometimes they'll wander off into the distance and not fill the gap or they'll fill it with some other nonsense. Or sometimes they won't engage in a creative uh uh dialogue with the designer because the author is dead and and and um all that stuff, and that can be great. But, sometimes they just just don't feel what you want them to feel.

**39:37** · So, the key here is theme. I'm I'm theme-first designer. Not everyone is.

**39:43** · But if you are doing an experimental game, a theme to hang all the mechanics on is great. And everything Cultist, everything in Sunless serves the theme.

**39:52** · Uh the art and music all are done in the service of um the intention that the game is going to be about yearning and apocalypse and experimentation. Now your creative direction, decide your theme, find two, three uh words to express it, make sure you keep tugging the theme back to that, and it's the equivalent of pointing the player's head direction the whole time. They're going to end up looking in the direction you want, and they're going to end up tending to think in the ways that you want.

**40:20** · Second point, a feeling design.

**40:22** · Do this.

**40:24** · Design can be beautiful. Mechanics can be beautiful.

**40:29** · Cultist, it's it's it's very clear what's going on. You might not understand all the ramifications of what you're doing, and you might not know all the combinations that will fire things off, but you very quickly learn the basic metaphors.

**40:40** · And here's something new in the last 5 years, 10 years, players are constantly more sophisticated in their appreciation of design and mechanics. Especially kind of people who play weird indie games you find at the shank end of Steam.

**40:57** · Uh and you will see people having much more nuanced discussions increasingly than this design sucks, this game is stupid.

**41:05** · Uh you will find people pointing out the things that work and the things that don't. If you make the design visible, if you you make your game like a skeleton watch, then that conversation becomes more thoughtful, the players can see what's going on. It makes it easy to educate your players on the design, which is something we said we wanted to do earlier, gets you better quality feedback, allows them to educate other people, and it allows them to give you better quality feedback cuz they can see what you're trying to do. You don't have to tell them your design intentions if you can actually they can see what your design intentions are.

**41:36** · They're hidden under layers of simulation, that's not the case.

### Cutting

**41:42** · And the final point, cutting.

**41:47** · You have a time and a budget.

**41:50** · Even if you're making your game as a hobby, it still has a time and a budget.

**41:54** · The time is your life, and the budget is all the money you will ever be able to spend in your life.

**42:00** · Everything is a timeline and a budget, and quick-paced experiments much, much more so.

**42:06** · At the beginning of a project, you'll have a list of features.

**42:09** · Uh and you'll know that you won't be able to put all of them in the project, and as the project goes on, you will find more features.

**42:17** · And um it's very rare for the feature list to shrink as you go.

**42:22** · So particularly if you're making a strongly themed experimental game, you want to cut down to the things that are necessary to have an effect. Richard Garfield's talked about a a complexity budget and thinking in terms of of adding features even if you can afford them. There's a limited amount of complexity you want in your game.

**42:40** · I think it's the similar thing with a a sort of thematic budget. If you put too many features in, your game isn't so much about something.

**42:48** · But it's really, really hard to cut. And um there's a a fundamental tension between creator and producer. And I'm not being snarky about producers here. My fiance and business partner uh is sitting there in the front row right now, and she's a producer, a very good one.

**43:06** · Um but designers tend to want to put more things in and make more things because we're really enthusiastic about them, and producers are the guardians of the budget and the timeline and tend to remind us that we only have finite hours, days, weeks.

**43:24** · And very often when Lottie and I work on Cultist, I would say this this has to go in, the advanced research stuff has absolutely part of my vision, do you not understand? It's it's so important, it leads into the primary pillar of experimentation. And Lottie would say, "Okay, but you did say that last week about that other thing. You said it was also absolutely vital, and nobody's noticed it's missing."

**43:44** · And the trick we found useful for cutting effectively was this.

**43:48** · Allow the grieving period and see how you feel at the end of it.

**43:52** · If you acknowledge the possibility of cutting something, even if you don't take it out of the list, if you say, you know, this is is is now going to a maybe or it's now going to a no, flirt with that possibility for a week, the end of a week, being a designer, you may well have thought of five other things that would achieve the same effect for less cost, or you may well have decided it's not necessary to the vision after all.

**44:14** · Or you may think, "No, good Christ, all the ripple effects of taking this thing out of the game would destroy the whole experience, we should definitely leave it in."

**44:22** · So give yourself a grieving period to think about whether you should take it out, and allow yourself a grieving period once you do.

**44:29** · Producers, allow your designers a grieving period, too.

**44:33** · So to review, the things I think have been successful, they've all been distinctive.

**44:41** · Uh they've all stood out in some way.

**44:43** · They've all been divisive. They've all had strongly boarded communities that have been advocates for them.

**44:48** · They've all been not dreadful, because you know, however much you argue that something's art, uh it's difficult to make it commercially successful if it's dreadful.

**44:59** · And the best way to get to that is to design the game to help you get the feedback.

**45:04** · All of them have had small budgets and constrained timelines. One day I'll make a game for $5 million, and it will be dreadful. But I haven't yet.

**45:11** · Uh and all of them rely on the suite of fancy-named terms I just talked about.

**45:18** · But this is why I named my first company Failbetter.

**45:27** · And I still love this quote, but I like this quote more.

**45:35** · So I I want to help you learn from my mistakes.

**45:39** · Here are a couple of things that we did differently in Cultist Simulator.

**45:45** · I said at the beginning that uh it can be an advantage not to have a genre.

**45:52** · Now that was true, but like many true things, it's a little bit more complicated than that.

**46:00** · Way too much text on this slide, actually. You've all stopped to read it now, so I'm going to let you do that.

**46:07** · So the point is, if you if something isn't really a genre, it's actually probably several genres welded together.

**46:11** · So Cultist Simulator, for example, was kind of an RPG and kind of a roguelike and kind of like Sid Meier's Pirates and kind of a bunch of other stuff.

**46:21** · But um it had a lot of RPG elements, a lot of roguelike elements.

**46:25** · And that was intentional, and to a large extent that was good, because it meant that you had the uh story part of a RPG with the peril part of a roguelike. So you really every time you venture out on the black ocean in Sunless Sea, uh you feel the fear to begin with.

**46:45** · But the problem with that, of course, as all the reviews very reasonably said, is that that's great the first three times.

**46:53** · Then after that, because it's not really a roguelike, it doesn't have enough variation in the beginning. That was my big design mistake.

**47:00** · You repeat the same story, and however beautifully written the story, it's not interesting the fifth time you read it.

**47:05** · It starts to feel like homework.

**47:07** · So if I had identified earlier where that fault line ran and the problems of having something that was both kind of an RPG and kind of a roguelike, I could have started building in mitigating factors earlier. This is something I said in my Kama Sutra uh retrospective, in fact. So if you're doing something that draws from different genres, there will be a fault line because some of the assumptions and expectations won't mesh. Find that fault line early. Find it earlier than I did, and you'll do better.

**47:35** · Same thing with Cultist.

**47:40** · The reason that Cultist has no tutorial is that I wanted the experience of playing Cultist to be the experience of the character.

**47:49** · I wanted the player to be slowly trying to understand what lies underneath the surface of the game and to have moments of discovery and of terror in the same way that the character who's starting to uncover the occult and the hidden world has moments of discovery and terror. When that works, it really works, and it's what people like about the game.

**48:09** · But it doesn't always work. Sometimes it's just just not accessible enough to people, and sometimes two of the genres rub up against each other badly.

**48:20** · So it's an exploration game, there's no tutorial, so you can find things out as you go, but also um one of the big influences on it was was RNG clicker games, having that that sense of slow uh sorry, clicker games with a bit more RNG, having that sense of slow accumulation of resources, and being able to spend resources on things. So I wanted the resource management in there because I like resource management in narratives, and because I wanted that sense of peril from the exploration that would come with knowing the game could be ended.

**48:52** · Very often, halfway through Cultist Simulator, either in a game of Cultist Simulator or in a player's experience of Cultist Simulator, you get to the point where you sort of understand what's going on, you've done all the exploration stuff, and you're still trying to get the loot you need for an expedition. Now I fixed some of that later on. I I took a lot of the RNG out of the game, and I made the game shorter, but there's this fundamental tension there between the exploration stuff and the uh resource management and the RNG clicker stuff.

**49:21** · I think that uh that could have been fixed. I think if I'd been a better designer, it would have been fixed. I think if we'd spent twice as long on the game, it would have been fixed.

**49:31** · And I think if I'd been more aware of it earlier and had directed my efforts toward mitigating it, it would have been fixed. So so look for the fault line if you're doing stuff that's cross genre because I don't always think of that.

**49:45** · This is something that EDC actually bought actually asked me. It seems a bunch of the criticism of the game then the UX is this something you felt was as designed or was this a fallout from the process of decisions you made?

**49:55** · So the answer is a little bit of column A and a little bit of column B. In fact, a little bit of column C.

**50:06** · The game's intentionally obscure.

**50:08** · Some of the uh limitations of the UI are there because I didn't want everything to be visible. Some of it for other reasons.

**50:15** · So there are no tooltips in Cultist Simulator.

**50:19** · It's partly because I didn't want people to get that sense that you could mouse over something and get it. You have to click on it. You have to dig a little bit deeper in into it. The other very pragmatic reason was we wanted to do a mobile version. So I didn't want to bake tooltips into what people expected from the game. It was tooltips on mobile are hard and because I learned that lesson when we did of Fallen London.

**50:39** · But part of it is intentional.

**50:41** · Part of it is mechanical limitations because the whole flow of the game is about putting cards experimentally in slots and kicking start to see what happens. That works wonderfully when you're translating a text into another text using a language or when you're putting different ingredients in rights to see what creatures they'll summon. That that works great.

**51:00** · But because I tried to do everything in the same mechanical metaphor, it's less ideal when you're sending people off on an expedition and you're mixing expedition locations with people and funds.

**51:12** · It just it it's it's harder for the player to understand what's going on.

**51:15** · It's stuck in that that one particular metaphor.

**51:19** · But that did also make it much easier for me to make the game because once you have the framework in place, I could just keep on cranking out content and the it's a very content-driven game.

**51:27** · Almost all the behavior is is specified in in the JSON text files.

**51:32** · Final thing of course is lack of polish.

**51:34** · This is a a peril you're up against when you're making a game that's experimental on a short timescale with a limited budget, especially if you are primarily a writer and UX is your your weakness as it was mine. I got a very talented UI designer, Martin Nerurkar, in to help with that and Catherine Unger made the game look great, but I I you know, it's not my strength.

**51:59** · And this was my big lesson is that I said earlier you can only go so far with it's art so it doesn't need to be good. That goes double for UI.

**52:12** · You want to give players an idea of where the edge of the piste is so they know when they're going off piste.

**52:16** · They're dealing with an unfamiliar experience with lots of of um peculiar design choices. You don't want to disorient them.

**52:26** · Also, I I've said a couple of times in this talk already, educating your players about your design intentions is vitally important because it allows them to give you better feedback and it allows them to educate other people.

**52:41** · And if the UI is murky, it's like looking through a smeared glass window.

**52:46** · So ideally don't obscure your design intentions between the UI like I sometimes did.

**52:54** · Finally uh I'm not alone in this. Uh if you are doing an experimental game and a small team and somebody on the internet says "Well, it's just rubbish, isn't it?"

**53:08** · It's very tempting to say "You don't understand my vision."

**53:13** · And if the UX is clear, if people can see what's going on it's much harder for you to hide behind that in a moment of despair or or arrogance. So it keeps you honest, give the players handholds to hang on to and both requires and allows you to be clear about your design intentions.

**53:32** · In the sum be you That's my talk.

**53:37** · Thank you very much.

**53:44** · And we have 6 minutes and 27 seconds for Q&amp;A.

**53:51** · Hi. Hello. Hi. Thanks so much. Um I'm curious you touched a lot on the why of not including a tutorial and I think it was a great decision, but I'm curious about when in the development process that decision was made and how it might have required you to revisit some of the mechanics or changes or if at all.

**54:09** · Excellent question and it was when in the design process to decide not to put a tutorial in. So I decided this very early. And one thing I didn't touch on in the talk because it's more design talk than a production talk is that if you leave something like a tutorial out, well done, you save 10K off your budget, which is a bonus.

**54:27** · But um so that was the intention from the start, but about 2 months before launch, my co-founder and our publisher both started to get very nervous about it because a lot of people would start playing the game casually and they just bounce off it.

**54:40** · And when we took it to an event, a lot of people said I I keep putting the cards in the slots and nothing happens.

**54:47** · And um Lottie and Humble both said "Maybe we should consider putting a tutorial in." And I said no, vision. And and more seriously, it it if if we start telling people what they can do early on, they they won't experiment. They'll expect to have their hand held later and it won't be as interesting.

**55:06** · And as so often when you've got a a design tension like that, um it was resolved by finding a third way, which was to radically limit the number of cards you could put in particular slots.

**55:17** · It used to be you could put any kind of card in any kind of slot. We said no, the only things that can go in the work slots are abilities, doobs, rights. And that meant that nearly every combination in the game that's possible has some sort of effect.

**55:30** · So the player doesn't feel they're banging on a wall and listening for an answer. They feel they're they're they they always get a response. The game is having a conversation with them. So that's the answer to that.

**55:44** · Hello. Hello.

**55:46** · Hi. Um I thought it was really fascinating how fast the turnaround in a lot of your projects have been. Said 11 months, 16 months, uh as little as 4 months for the year release of Fallen London.

**55:57** · But you also mentioned that you feel like something you would do differently is try to include more polish or things like a tutorial maybe. What is the process for determining when you're done with the game? Like when it's going to be released? Is it purely budgetary concerns? Like it has to come out now to continue as a a company or Yeah. What is it? So um another excellent question is how do we decide when we're going to finish production on these very short timescale games?

**56:26** · And what uh the answer is to play chicken with deadlines, I think. Uh I'm a big believer in deadlines promoting ingenuity. I take them seriously and we when we took uh the game to events early on, we actually had our deadline printed on the banner. Um I said that it would be we did the run the Kickstarter in September. I'd done 3 months production previously. Released in May and and and we said 31st May was the deadline and people came out to us and said "That's a bold choice printing your your deadline on there."

**56:56** · But it holds us to account. We didn't crunch. We worked a bit of overtime towards the end and we got ratty with each other, but we just cut like crazy.

**57:05** · In terms of polish next time I think we would do, this is this is what we discussed, fewer features and a bit more UI work. I think that's what would have made the difference. It's it's prioritization.

**57:19** · Working to tough deadlines also really sharpens your estimation skills. It's much easier to work to deadlines once you work to deadlines.

**57:26** · But all that said, next time we're thinking about keeping a sort of a bucket of undefined time that Lottie will be the guardian of rather than me.

**57:34** · That I have to make the case for spending time on, but we'll see how that goes.

**57:38** · It's great. Thank you.

**57:42** · I have a question about failures. Yeah.

**57:45** · Specifically do you have any advice for drawing the line between calling something dead or uh starting over and trying something new to uh work with the same idea?

**58:01** · Uh so the question is is is where do you draw the line around failures when you call something dead? My answer, this may not be the question you're asking, but it's always ship it. If you think it's going to fail, finish it up and ship it anyway because even if it sells exactly zero copies, you will learn something from the process of finishing it and you will um uh issue regret.

**58:21** · I think I mean I said all those things are failures, some more failures than others. I think it's a little bit melodramatic. Um below for example uh never made its Kickstarter target.

**58:31** · Silver Tree uh did make its Kickstarter target. It it raised money for the company, kept people employed a bit longer, but it was not well received because because we didn't do a great job of it.

**58:40** · Uh I think yeah, it it let your audience decide if it's a failure, I think is the is the best answer I can give.

**58:48** · Thank you.

**58:51** · Hi. Uh great talk. Uh love the game.

**58:54** · Uh one question.

**58:56** · Uh what does the bird worm slider do in the options?

**59:00** · Trying to get a a canonical answer.

**59:03** · It it it allows you to choose between bird and worm.

**59:06** · No. Uh There is a it's uh we're all friends here, right? Uh hidden in the game is um I think it's pretty fancy to call it ARG. It's not really an ARG. It's a series of puzzles that lead to a series of rabbit holes. And if you fiddle around with the bird worm slider and poke around, you might find the beginning of that.

**59:27** · Okay. Thank you.

**59:30** · Uh Um, hello. So I played Sunless Sea and the Cultist Simulator. I I think both of them are very great. Thank you very much. And uh I just think also the mechanic is something that I am really impressed. Uh like the cards combine the card and the TRPGs gameplay and uh like put the cards into some actions to do something. I I just wonder how you get that idea.

**59:59** · Uh I I've always loved cards. Even before London was card-based. Um I think uh for two for three reasons, really.

**1:00:08** · No, I'll stick with two cuz we're short of time. For two reasons. One is that as a if you are a writer who likes short, concise, pithy text, then cards are great cuz they give you a natural limit to write to.

**1:00:23** · Um and and also if you are working on very low budgets, cards are great because to add content to the game, you add some text, you add some behavior, and you add a little image. Uh I guess the third thing is that they come with a bunch of expectations that fit into the metaphors you can then play with.

**1:00:42** · Uh like, you know, cards, you you you you often have a limited number of them.

**1:00:46** · Uh you often get rid of them by playing them. And it also allows you to subvert those expectations. Like in Cultist Simulator, some cards have a timer on them.

**1:00:56** · Contentment, for example, only lasts 30 seconds. And after 30 seconds, when you first see your card on the desktop, it'll suddenly burn up in a whisper of flame, uh you remember that moment.

**1:01:06** · So, did you get it from the very early stage of your design?

**1:01:10** · Um the very very earliest stage was the gray box JavaScript prototype, and I don't think I'd thought in terms of cards then.

**1:01:19** · But because I wanted to do something where the mechanics are exposed, um we very quickly got to the idea of a desktop with some sort of tokens or board game-like pieces on. And at that point, cards cards, for all the reasons I mentioned below, were immediately the the option. We We had a lot more time a lot more trouble narrowing down on the the tiles, the verbs. They were going to be gems, they were going to be drawers, they were going to be stones. But But cards were there as soon as you said it was board game-like.

**1:01:46** · Thank you. I'm sorry, Alex. We have run out of time, and we do need to move the questions across the hall to the wrap-up session.

**1:01:55** · Thank you. Thank you very much.