# Horde Encounter RNG Abuse Guide

There are 3 ways of triggering a horde in gen 6 games:
* Using Sweet Scent - Guaranteed horde
* Using Honey - Guaranteed horde
* Moving in the grass - 5% chance for horde

In this guide, we are gonna explain 2 of the 3 ways, Honey and Moving.
While Sweet Scent works in a way simillar to Honey, 
it suffers from unstable delays and no public tools currently support it due to different setup.
That said, from now on, we are gonna pretend that Sweet Scent doesn't exist at all.

# Tools

* [3DS RNG Tool](https://ci.appveyor.com/project/Bambo-Rambo/3dsrngtool/build/artifacts) (My fork)
* [Tiny Finder](https://ci.appveyor.com/project/Bambo-Rambo/tinyfinder/build/artifacts)
* [Pcalc](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) for 3ds or [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) for Citra Emulator

# Introduction

Like most gen 6 rng types, a complete horde encounter rng requires manipulation of both the MT and TinyMT states.
MT (Mersenne Twister / the initial seed), is used to generate the PID (shininess), the IVs (stats), gender (if exists), 
ability (if not HA) and the nature (unless force synced).

TinyMT (Tiny Mersenne Twister), is used to decide the encounter slot (species), the synchronize success, 
the chance of getting the HA and if doing the Moving method, the successful horde trigger.

For the MT part, we are gonna be using 3DS RNG Tool while for the TinyMT part, Tiny Finder, both getting info from Pcalc.

**To avoid any confusion between the 2 algorithms, I am gonna be using the term "frame" for a MT state and "index" for a TinyMT state.**

As for the frames, we notice that 3DS RNG Tool shows the PID and the stats of all 5 Pokemon in the horde for each frame.
The first five rows represent the resulting horde for frame 0, the next five ones for frame 1 etc.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde0.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde1.png)

If you have the shiny charm, you will be getting 15 identical shiny frames with the same traits.
This happens because the charm affects each Pokemon seperately.
Like Normal wild shows 3 identical shiny frames, here we have 15.
We will see later which of these to aim for.
Just keep in mind that each of these shiny frames is a different horde.

### Honey method - Prons and cons

* (+) Quite easy to find and hit your target index (getting the correct slot, sync etc)
* (+) No chance of failing the horde encounter
* (-) Unstable delays can result in getting the correct species but wrong stats, PID etc

### Moving method - Prons and cons

* (+) Stable delay (+6)
* (-) In ORAS, only possible at long grass
* (-) Will miss the encounter completely if not done right
* (-) The desired index might be very far away, may not have time to combine with a nice frame

There is no way to tell which method is actually "better".
Depending on the case/place, one may be more effective that the other.
I am gonna explain both and you can choose whichever works better for you.

For either of the two methods, I recommend using the NTR helper to connect your console to the 2 programms.

Connecting to 3DS RNG Tool will allow you to search for nice spreads faster, 
while Tiny Finder will read your TinyMT state immediately without having to type it manually every time.

# Honey Method

There is nothing really difficult here. 
After calibrating the delay for the main (MT) rng once, 
we are gonna prepare the TinyMT part to guarantee the correct species, nature sync and ability, 
then wait inside the bag with the Honey highlighted until we reach our target frame.

Make sure that you have already saved the game in the desired route/location beforehand.

### Searching for the desired frame

In 3DS RNG Tool, pick your location and the desired species.

Use the [reseed](https://github.com/wwwwwwzx/3DSRNGTool/wiki/NTR-Helper-Usage#note) method until you find a (shiny) spread that satisfies you.

If you care about the gender of the Pokemon, keep in mind that it may be the opposite of the one you see in the tool, 
if you plan on syncing the nature and/or manipulating for the HA.
In that case, check the "Assume Synced" box in the tool, select a random nature from the list and set the value of the "HA" box to anything between 1-5.
The frame(s) with the Hidden Ability will show the correct gender.
Don't set them as target frames yet, I will get back to this later.

### Getting Started - Calculating the Honey delay

Load the game and enter the bag. 
The first try will be random in order to find the delay for our current locaton.

Inside the bag, highight the Honey and press 'A' once so you will be ready to use it.

In the "Generator" tab of **Tiny Finder**, select the "Horde" method, 
choose your location or check the "Cave" box if needed and carefully put the exact number of Pokemon in your party.

**Don't mess with the "Preferences" section yet, or if you did, check the "Ignore Filters" box.**

Click "Update" and the tool will read and show the results for your current TinyMT state.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde2.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde3.png)

If I use honey now, I am gonna hit index 0 in the first row.
In this case, synchronize will not work and the species will be five Zubats (slot 1 in Meteor Falls) none of which will have their hidden ability.

You can find the encounter slots for gen 6 encounters including hordes [here](https://sites.google.com/site/pokemonslots/gen-vi).

This step is necessary because, for 3DS RNG Tool to calculate the results (PID, stats etc) accurately, it needs to know the above info (HA, sync).

So according to index 0 from Tiny Finder, I return to 3DS RNG Tool, choose "Zubat" in "Meteor Falls (2)" location, 
leave the "Assume Synced" box unchecked and don't change the HA number.

In order to find the delay, I freeze the game by pressing Start + Select at frame 50382, 
I set it as target frame in the tool (Right Click -> "Set as Target Frame") then hold 'A' to unfreeze and use the Honey.

(I recommend having all 3 Pcalc menus open in order to have more stable delays.)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde4.png)

By pressing Start + Left, we can see the wild Pokemon's stats (to shift between different Pokemon in the horde tap Select + Right).

As expected, the TinyMT part is correct. 5 Zubats, random natures even though I am leading with synchronize and no HA either.

Spread is: 30/18/1/29/1/9 so I am gonna put it in 3DS RNG Tool and press "Calculate" to find how off I was.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde5.png)

Notice how the tool shows 5 simillar frames with the same spread. 

I can easily tell I landed on the 5th though (50374) since Pcalc showed that this spread belongs to the 1st Zubat (Horde Pokemon 1) so I am looking for the slot 1 frame.

(Keep in mind that the term "slot" here, implies the position of the Pokemon in the horde. No relation to the encounter slots at all.)

To calculate the delay, just take the number from the "Shift/F" column and add it to the current delay.

174 + (-8) = 174 - 8 = **166**

### Finding the right index, hitting our target

Run away from the battle, and enter the bag again.

In Tiny Finder, choose the encounter slot you want to hit, select "Any slot" for HA if you want your target to have its Hidden ability, 
check the "Sync" box if you want to sync the nature and if playing ORAS, ignore the flute boxes unless you care about the exact level of the Pokemon.

Press "Update" and these are the indexes that meet your requirements.
You may target any of them (probably the earliest one).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde6.png)

The earliest index with slot 3, HA and nature sync requires 49 advancements.

Here are some ways to advance inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 index (In fact what advances here, is checking the summary screen of the Pokemon). Don't actually teach the move, otherwise unwanted advances will occur. Don't stay in the move selection screen for too long, otherwise unwanted advances will occur.
* Giving your Pokemon a held item, usually advances by 3 indexes (rarely by 4).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes.

I have 5 Pokemon in my party so there will be 5 * 3 = **15** advances per Exp share usage.

Since I need 49, I can use the Exp Share 3 times (15 * 3 = +45), give one of my Pokemon a held item (+3) 
and finally attempt to teach it a new move (+1).
The total is (45 + 3 + 1) = 49 and that's pretty much it.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde7.png)

There we go!

My current TinyMT state matches the one of my target index.

It is now guaranteed that using Honey here, will generate a horde of 5 Jolly (my leader's nature) Bagons where the 2nd one will have its Hidden ability (Sheer Force).

Time to track down our exact target frame(s) so we know exactly when to use the honey, one more "tricky" step and we succeed.

In 3DS RNG Tool, choose "Bagon" in "Slots", change the HA number to 2 and adjust the Nature settings.

In the following image, frames 279306-279308 are the ones I should go for since they have the HA in slot 2, 
so I just need to wait until I get there, with the Honey ready for use and all 3 Pcalc menus open.

Notice how the gender for all those shiny frames changes from female to male after the "Assume Synced" box was checked. HA didn't affect this time.

I am expecting the shiny with the HA in the second spot (from right to left) of the horde.
Let's go!

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Horde/Horde9.png)

# Moving Method (Pending)
