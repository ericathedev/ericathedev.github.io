---
layout: post
title: You are an archaeologist (5 tips for navigating legacy systems)
date: 2020-05-06 18:00:00 +0200
tags: refactoring beginners
excerpt: You are an archaeologist. When you're at school building your own greenfield projects by yourself, this is a skill you don't get to learn. However chances are, when you start your developer career, you'll be working on a project which has been around for some time.
---

You are an archaeologist. When you're at school building your own greenfield projects by yourself, this is a skill you don't get to learn. However chances are, 
when you start your developer career, you'll be working on a project which has been around for some time. This means you are navigating through a system built 
on layers and layers of commits by different people. You probably have partial knowledge about the thing you're excavating. And you need to be careful not to 
break anything.

Here are some tools for your toolbox to help you be a better archaeologist.

# 1. Excavate the git history
I learnt this one early on in my career, and it's one of the number one tools in my toolbox to this day - Excavate the git history (only when I started, it was SVN 😬🤣).

What should you be looking out for?
- Read the commit messages: The commit messages are (hopefully!) going to help you look into the intent behind the code, or at least their changes. Does it have 
an issue number which might provide more context behind the change?
- How long ago was the specific piece of code you're looking at changed (so for example, that specific method)? How often was it changed? Is it one person, or many 
people? When was the first commit? This will tell you the story of the layers of the code and how it all evolved over time - or didn't, which raises a whole other 
host of questions. 
- Look at the authors - is there anyone you can reach out to with any questions you might have?

# 2. Divine meaning through tests

Hopefully the code is tested, and hopefully those test names have some kind of format. For example, the format I generally tend to use is 
`MethodName_StateUnderTest_ExpectedBehavior`. Small (unit) tests can help you understand how a specific method or class works. Larger tests (like black box 
tests) help you understand what is happening at a feature level.

# 3. Search the archives of your documentation

The trick here is knowing where documentation may hide. Varies from  project to project or company to company. Some examples of documentation to look out for 
are READMEs, Wikis, API documentation (for people integrating with the API), formal specifications documents and user guides. Just because the documentation 
wasn't intended for you (as a developer), it doesn't mean it isn't useful. Often understanding a user's perspective can be just as valuable, especially if you 
don't have any understanding of the product or feature and its use.

# 4. Run the code and check (or add) logs

It might sound primitive but sometimes the best or only way to understand a piece of code is to run it. That gives you what's called a "black box" understanding, 
where you don't know anything about the code that is running. To turn that into a "white box" understanding, look at the logs to see which pieces of code are 
being exercised when you use certain features. If you are trying to understand a specific piece of code, you might need to add more detailed logs to get more 
information! It's then up to you to figure out which logs should be committed, and which were just useful to help you to understand what was going on.

# 5. Don't be afraid to get your hands dirty

The great thing about being a developer is that, unlike an archaeologist, you get a trial run. You can mess up the archaeological dig, make a bunch of changes to 
learn, and then stash everything and pretend like it never happened. I find this really helpful when I can feel myself getting into 
_[analysis paralysis](https://en.wikipedia.org/wiki/Analysis_paralysis)_. 

So start typing! Sometimes it's nice to get right to the refactoring - extracting and renaming variables and methods to make the code more readable. If the code 
is so difficult to understand that you really don't know where to start, an easier step can be writing comments to explain what (you think) the code is doing, 
or leaving questions which you'll hopefully be able to answer later. 

It might seem like a waste of time to start making changes when you're not sure if it's the right way to go, but sometimes you'll never know if it's the right 
way to go without trying to make the changes!

_Happy digging! What are your favourite legacy code navigation tips? 💭_
