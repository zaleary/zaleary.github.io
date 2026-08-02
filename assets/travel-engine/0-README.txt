# A travel engine that knows your taste

You have six files. Dropped into a Claude project, they interview you about places you already love, build a model of your taste out of that, and turn the project into a recommendation engine that runs against it. 

After setup you name a city and get places chosen for you specifically, researched live rather than recalled. Or let it pick a city for you.

Setup is one conversation of about an hour, plus two short ones after to validate.

## What you need

Claude, with projects and web search. Nothing else. No code, no accounts, no API keys.

## Optional, your Google Maps saves

If you save places in Google Maps, exporting them gives the interview real anchors to work from. It is genuinely optional and the interview works fine without it.

Go to takeout.google.com, click Deselect all, tick Saved, and export. You will get a zip with one CSV per list (Want To Go and Favorites, for example). Drop those in with the other files.

Worth knowing two things. If you have fewer than about a hundred and fifty saves, or they are all in one category, skip it, the interview will tell you the data is too thin anyway. And the export only helps with what you like. What you dislike, and how you choose destinations, come out of the conversation either way, because Google Maps only records what you saved.

## Setup

**1. Make a project and drop in the files.**

Create a new Claude project, call it whatever you like, and add all six files to its knowledge, this one included: 0 README, 1 START HERE, 2 Method, 3 Interview, 4 Skeleton, 5 Calibration. 

Add your Takeout CSVs if you have them. Leave the project instructions field empty for now.

**2. Say "Start setup".**

Open a conversation in the project and type it. Claude will check the files are all there, then start interviewing you.

This takes an hour and you can do it across several sittings, just come back to the same conversation. It is a real back-and-forth, not a form. It will push back on you, ask about places that do not fit the story you are telling, and reflect drafts back for you to correct. The corrections are the point, so argue with it.

**3. Save your profile.**

At the end it hands you your profile. Save that message as a plain text file called `Preferences.md` and add it to the project's files.

Before you close the conversation, it will ask you to write down five to ten places you love in one dense city you know well. Keep that list somewhere outside the project, in a notes app or on paper. It is your answer key for the next step and it has to stay out of Claude's reach.

**4. Start a new conversation and say "Calibrate".**

Do not skip this step.

The engine runs cold against your chosen city, using only your profile and web search. Then you check it against your list and tell it what it missed, what it got wrong, and what it got right for the wrong reason. It works out which of those are bugs in your profile and proposes fixes.

It should also delight you.

Your profile after the interview is a first draft. This is what makes it real. It also gives the engine a permanent depth reference in your own taste.

Then update your profile, in this order. Delete the old `Preferences.md` from the project's files first, then save the new one it gives you and add it. Delete before you add, or the project ends up holding two profiles and the engine reads whichever it happens to find.

**5. Start one more new conversation and say "Bake".**

It will tell you which files to delete, they are spent, then produce your finished instructions. Copy that message into the project's instructions field, replacing anything there. Keep `0 README`, `1 START HERE`, and `2 Method`, you need them any time you want to rebake.

That is it. You are set up.

## Using it

Start a new conversation in the project and try any of these.

**Recommends places in a city you have picked.** Lisbon, five days in early November. You get a curated menu grouped by neighborhood, with reasoning for every pick and a routing note at the end. It is a menu, not an itinerary, you string your own path.

**Judges one specific place.** Would I like Bar Alimentar in Lisbon. A quick verdict with the evidence behind it.

**Answers fast while you are already there.** Dinner tonight within a fifteen minute walk of Príncipe Real. Two to four options with confirmed hours.

**Picks the destination for you.** Where should I go for a week in October, leaving from Philadelphia. It needs where you are leaving from and when, and it is the one to use when you have a window but no idea.

Whichever you use, give it a real destination and let it work. It searches heavily and the first response takes a while.

It will also tell you when it cannot find anything good rather than padding a list. An honest dead end is more useful than five mediocre suggestions.

## Give it context

The engine never asks you follow-up questions. By design it takes what you give it and makes the call rather than interrogating you, so anything you leave out just gets defaulted quietly. Any of the four modes gets materially better with a little more to work with.

Your dates or how long you are there is the big one. It drives the season read, which places close on which days, and whether the engine can price a hotel at all.

Who is coming, since your profile may behave differently with company. Where you are staying, so routing anchors to it. And anything true only for this trip, a dietary need, a bad knee, no museums this time, we have a car.

So rather than Lisbon, try Lisbon, five days in early November, with my partner, staying in Príncipe Real, she is vegetarian.

## Maintenance

The profile you finish setup with is a starting point. The engine gets better at you over time, but only if you feed it, and everything below takes a couple of minutes.

**When it gets something wrong, say so.** After any correction it proposes a one-line amendment to your profile. It will also ask, once per conversation, whether anything in a set of recommendations is off. That question is worth answering even when the answer is small.

**After a trip, ask for a postmortem.** This is the highest-value thing you can do and it is the one people forget. Tell it you went, and it will walk the trip with you, what you actually did, what you skipped, what the best thing was and whether it found that or you did, what underdelivered, what it missed entirely. A single postmortem is worth more than a dozen in-conversation corrections, because you now know things about your own taste that no interview could have reached.

It comes back with a set of amendments rather than one, split into changes to your taste and updates to your destination ledger, which is the running note of where you have been and whether you would go back.

**Fold amendments in.** Paste them into your `Preferences.md`. Then delete the old copy from the project, add the updated one, and say "Bake" again. Amendments do nothing until you rebake.

**Recalibrate occasionally.** Say "Calibrate" in a fresh conversation and point it at a different city you know well. Worth doing after your first real trip, and any time the recommendations start feeling slightly off in a way you cannot name.
