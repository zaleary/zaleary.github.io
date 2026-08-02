---
layout: post
title: The Travel Engine
date: 2026-08-02
---

*This is a set of files you drop into a Claude project. It interviews you for about an hour about places you already love, turns that into a model of your taste, and from then on you name a city and get back places chosen for you specifically, researched live and checked that they're actually open. It can pick the city too, if you don't have one. Files are attached.*

## Addicted to Second Brains

I save everything in Google Maps. Restaurants, bars, coffee shops, statues, whole neighborhoods I want to walk through. A couple thousand pins accumulated over years, pruning Want To Go as I visit, with the great stuff ending up in Favorite Places. It's a pretty good record of my taste, and it makes it easy to zoom in on a city to find places I want to go or want to brag on. What it can't do is explain itself. A couple thousand pins and almost none of them say why.

A while ago, I started trying to turn that pile into something that could actually recommend places to me. I tried a few things that didn't work, a different story for another day. What I ended up with is not what I set out to build, but it works well enough that I want to hand it to other people.

The problem I was actually solving is that asking an LLM where to eat in a city gets you the same answer everyone gets. That happens for two reasons. First, it doesn't know you, so it optimizes for the median traveler, and the median traveler wants things I don't want. Not just because I'm super persnickety, but because I'm an individual. Second, a model recommending from memory is recommending whatever it learned before its training cutoff, which can be a fossil record of fame rather than a picture of what's good now. Places close. They decline. Places open and get great, but nobody's blog post has caught up. 

## I Can't Describe My Own Taste, Can You?

Long story short, I had an LLM interview me instead. Not a questionnaire, because if you ask someone what they value in a bar they will say good drinks and nice atmosphere and you've learned exactly zero. 

One thing did survive from the original project. I exported all that Google Maps data and dumped it into the interview, then had it pull real favorites from the categories I care about. I had it look for outliers in those categories to suss out what doesn't fit the story I'd tell about my own taste, and asked me to react to them. What do these have in common? What separates the ones I'd go back to tomorrow from a one-time visit? What does this category never get right?

That's where the real material was. Things I knew but never said out loud. Tacit knowledge. That a coffee shop should be generative, a launching point for a day, not just brew a good cup. That the enemy in fine dining was never formality, it was formality without love, the childlike-wonder moment a great room engineers and a mediocre one skips. That craft is judged relative to a place's own ambition, be great at whatever you are, high or low. That popularity and awards aren't proxies for quality, they're unvalidated claims that have to be checked against current form.

Six categories and an hour later, that became a structured model of my taste.

## Turns Out I Will Wait in Lines

I've put the engine through its paces a few times since. First in San Francisco to test against a city I know and love. Not only did it nail the places I'd have picked myself, it also got me to a cocktail bar I'd never even heard of, and that I truly adore: Stoa.

The most thorough test so far was Kraków, and it took me on a whistle-stop tour of hits, several of which I'd never have found on my own in time for the trip. It also got things wrong in specific, fixable ways, and every one of those fed back into the engine to make it run better. Verify places aren't closed before spending time to convince me to go. Don't treat a fifteen minute queue as disqualifying at a place worth queueing for, even though I explicitly said I don't like to wait in line. Don't send me to a bar with an amazing vibe that only shows up around the time I'm hoping to be in bed.

## Sorry, What Does This Do?

What it does now, in short. You name a city and it researches it live and returns a menu grouped by neighborhood, every pick reasoned against your profile, every place verified open, and a route note showing how it could all string together. You can name one specific place and get a verdict. You can give it a time and a radius when you're already there and hungry. 

It can also pick the destination itself. Tell it where you're leaving from and when you're free, and it does the rest. The trick is that it doesn't rank cities on reputation. It runs a quick version of the place search against each candidate and scores it on what actually comes back. So a famous city that wouldn't really feed you ranks low, and some second city you'd never have considered ranks high because it turns out to be full of your kind of thing. I didn't expect that to be the part I'd use most, and I really didn't expect Riga on my bingo card this year.

It will also tell you when there's nothing great, finding the best of the rest and stating it up front, rather than padding a list to look useful. That took some doing and it's one of my favorite things about it. Looking at you, Myrtle Beach.

## You Want One

As of now, it runs entirely inside a Claude project. No code, no accounts, no API keys. You drop six files in, say a phrase, and it interviews you.

The honest cost is about an hour. But it's an hour of talking about bars and restaurants you love and arguing with something about why you love them, which is not the worst way to spend an hour if you really care about this sort of thing, and from testing so far, the interview itself is the fun part.

After the interview, the engine runs itself cold against a city you already know well, so you can check its work before you trust it anywhere unfamiliar. Don't skip it. It fixes things, and it earns your confidence.

Files are attached. Start with the README, it's five steps.

If you build one, I'd love to hear what it got wrong. That's how mine got good.

<div class="downloads">
  <span class="label">Download the kit</span>
  <a class="download-link" href="/assets/travel-engine/0-README.txt" download="0 README.md">0 README.md</a>
  <a class="download-link" href="/assets/travel-engine/1-START-HERE.txt" download="1 START HERE.md">1 START HERE.md</a>
  <a class="download-link" href="/assets/travel-engine/2-Method.txt" download="2 Method.md">2 Method.md</a>
  <a class="download-link" href="/assets/travel-engine/3-Interview.txt" download="3 Interview.md">3 Interview.md</a>
  <a class="download-link" href="/assets/travel-engine/4-Skeleton.txt" download="4 Skeleton.md">4 Skeleton.md</a>
  <a class="download-link" href="/assets/travel-engine/5-Calibration.txt" download="5 Calibration.md">5 Calibration.md</a>
</div>
