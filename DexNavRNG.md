# DexNav RNG Abuse Guide

### Because PokeRadar shiny patch RNG was only the beginning!

Ever wanted to find a perfect 6IV shiny in the wild that has its hidden ability and an egg move it could not learn otherwise?

Follow this guide for **RNG abusing** DexNav mechanics and enjoy the full potential of this amazing ORAS exclusive feature!
A Pokemon flawless in every aspect (shininess/stats/ability/egg move/gender/level) is an absolutely realistic target even without the use of emulator.

If you want to catch easy and fast shinies without caring too much about stats and other traits, 
then [Normal Wild RNG guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md) may suit you better.
In any case, it's the base for TinyMT RNG which I highly recommend becoming well familiar with, before attempting DexNav.

This guide will provide you with some useful tips to save time and effort but don't expect to succeed in a few minutes without prior experience.

You will be able to rng for all species that appear in a given location including DexNav exclusives of course, 
but not the ones that only appear in hordes, breakable rocks (rock smash) or by fishing.

### Tools needed
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder) (The most up to date build - The main tool for this RNG)
* [3DS RNG Tool fork](https://github.com/Bambo-Rambo/3DSRNGTool#forked-from-wwwwwwzx3dsrngtool) (This version has DexNav RNG implemented unlike the official version)
* [Pcalc G6](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) or [PokeReader](https://github.com/zaksabeast/PokeReader)
for **3ds** or [CitraRNG fork](https://github.com/Bambo-Rambo/CitraRNG) for **Citra Emulator**

### Recommended
* Max Repels
* Leading with a Pokemon with synchronize ability if you want a specific nature
* If playing on console, it will be helpful to keep one side of the bag empty (We will see later why). I discarded all my Berries since I don't have any use of them

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav1.png)

# General Info

Despite the increased difficulty, the main advantage of DexNav RNG over Normal wild RNG 
(apart from the countless [extra benefits](https://bulbapedia.bulbagarden.net/wiki/DexNav#Special_qualities) and DexNav exclusive Pokemon)
is that, similarly to PokeRadar in XY, we can generate guaranteed **shiny patches**.

This means that IVs and shininess use a different prng state for generation, speeding up the process of find high IV shinies a lot!

Even better, unlike Pokeradar, building a chain is not required (although it helps) for shiny patches so users may rng for them instantly upon booting the game.
Here are some [more differences](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#differences-between-dexnav-and-pokeradar) between PokeRadar and DexNav to get the main idea.

Now most people including shiny hunters use the "Search function" in the touch screen to guarantee the desired species and avoid getting the wrong shiny.

Regarding RNG abuse though, this method is not consistent because it results in unstable delays and more important, 
is affected by the random NPCs movements that advance the prng state unpredictably.

Instead, we are going to abuse this 50% chance of "randomly" triggering a hidden Pokemon by moving (walking/turning) close to the wild area.
The idea is to make **19 turns (or steps)**, do the necessary advances and finally **rotate** the character at the right time and succeed.
As said above, horde/rock smash/fishing exclusive Pokemon **do not** spawn with this method.

# Getting Started

### Step 1 – Choosing the target TinyMT Index in Tiny Finder

The **TinyMT prng state** determines species (slot), shininess, HA, egg move, potential, held item, nature sync and level boost (+10).

The **MT state** mainly determines IV spread and gender.
If shiny, HA and synchronize checks fail from TinyMT though, MT determines the values of PID, ability (1/2) and nature.

We are looking for a good TinyMT index first because the only way to get a new seed is by resetting the game.
When we find something that covers our expectations, we will focus on the MT seed which can be refreshed pretty quickly (takes around 5 seconds if you are using the NTR Helper).
We don't want to find a frame with a nice spread (MT) only to realize that there are no good TinyMT indexes to combine with.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#setting-up-tiny-finder) on how to setup Tiny Finder depending on your preferences,
as well as understand how the Search Level and Chain length affect the results.

When you are done, it's finally time to boot the game.

Connect your console **to 3DS RNG Tool first** then to Tiny Finder using the NTR Helper and when the [first cutscene](https://camo.githubusercontent.com/0ad13238fe4c81572505be45e2fc78cd864f9e0c5abf7ff3d1809d6da1bd23f0/68747470733a2f2f692e696d6775722e636f6d2f6c38534c4b62622e706e67) loads, 
press `Update` in Tiny Finder.

It will read your initial TinyMT state automaticaly, as well as your current step counter and the current chain length (both set to 0 when booting the game obviously)
and will then update the list with possible available results to choose from.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#dexnav-results) how to read the results from Tiny Finder.

If you didn't find what you were looking for, set the chain length to 4, **uncheck** the checkbox to prevent the tool from resetting it to 0, and press `Update` again.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav2.png)

A 4-length chain takes 2-3 minutes to build and is totally worth it, unless you are looking for a low level Pokemon on purpose (so the +10 level boost should be avoided).

If you still didn't find the desired index, hard reset (or soft reset if using Pokereader) your system and try again.

### Step 2 – Choosing the target MT frame in 3DS RNG Tool
You have found what you were looking for, so it’s time to focus on the main frame and choose the IVs of your target. 

In 3DS RNG Tool, choose `DexNav` and set up the tool **according to your target index** in Tiny Finder.

**Important: It's impossible to advance more than 3 to 3,5 TinyMT indexes per frame so set the Min Frame to something HIGHER than (your target index / 3) to be sure. 
My target index is 41800 so I set the Min Frame to 20000 (41800 / 3 ≈ 13933).
More details in a bit.**

As shown in the previous image, my index guarantees shininess, has the Hidden Ability, successfuly syncs the Nature and has 3 perfect IVs (potential) so I set up 3DS RNG Tool like this:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav3.png)

If your target is Unown (Mirage Cave only), check the corresponding box to make it show the form/letter for each frame.

Note that the delay tends to be a bit **unstable** sometimes so it’s better to search for 3-5 consecutive identical frames (I take the risk here with 2).
This will also solve the odd/even frame issue.

You may now pick any frame of your choice. 

# Prepartion

If you have filtered the results to the maximum, your target TinyMT index is most likely very far away and you will need to advance thousands of indexes.
The fastest way is going to a rainy place and wait there (Route 120 always works, just move down to the map a little and a heavy rain will start). 
You can also activate the Pokemon Amie function at the lower screen of your system.

* Rain advances by 3 indexes per frame advance
* Pokemon Amie advances by 0,5 indexes per frame advance (apparently doesn't work if you have interacted with strangers in the PSS)
* Combining these 2, results in advancements of 3,5 indexes per frame so you can approximately calculate how much time you need to stay there. Leaving a bit earlier is suggested so you won't miss your index.

In the following image, I make use of both.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav4.png)

When you get close to your target index, return to your location 
(If you have to build a chain, I suggest returning around ~1500 indexes before your target otherwise the suggested number is ~800).

Check the coordinates of your index in Tiny Finder and find an appropriate tile to stand on. 
Remember that the resulting patch must fit INSIDE the grass (or water if you aim for an aquatic encounter).

In any case, you should stand somewhere OUTSIDE of grass or water because moving inside them, causes (2) unwanted advancements (inevitable in caves).

Build up your chain if you have to (check [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#chain-building) how to build a successful DexNav chain without breaking it), 
stand on the correct spot, press `Update` to refresh the Step Counter and take the remaining steps/turns until it reaches 19.

### Finding the noise for your current spot

**Skip this step if you are sure there are no (running) NPCs nearby.**

When closing the X menu and the character is free to move again, 
the NPCs influence (blinking/moving) starts taking effect and we need to find out if this happens immediately after closing the menu, or a bit later in which case it won't be an issue.

For Normal Wild RNG, the tool takes that into account (since the suggested spots are specific), 
but since your position in DexNav RNG varies, you have to calculate the noise yourself (0 in most cases but still).

Press `X` to open the menu and then freeze the game by pressing `Start + Select`.

While the game is frozen, hold down `X` and tap `select` 10 times, in order to close the menu slowly.

If you notice the TinyMT state changing in the 10th press, take note of how much it advanced and set `Calibration` to that number (usually 0 as said, rarely 1 and almost never 2).

# DexNav RNG

Let Poke – Amie and the NPC influence advance for you.

When you are about 50-55 indexes away (keep pressing `Update` to keep track of advances), **CLOSE POKE – AMIE** and enter the bag.

The TinyMT state **does not advance inside the bag** on its own, so we have full control now.

At this point also, Tiny Finder will have set the `Min Index` value to something, based on the selected location.
This is the number of advances consumed **upon exiting the bag** (you cannot hit anything lower) and we need to account for that 
(it's usually 15, sometimes 3 in caves etc but I recommend making a test for your current location/spot to be sure).

Just advance the TinyMT state until the value of `Min Frame` matches the one of your target index.

Here are some simple and consistent ways to advance inside the bag:

* Turn on/off the EXP Share to advance by 3 * party number. If you have 5 Pokemon in your party for example, using the Exp Share, advances 3 * 5 = 15 indexes.
* Give your Pokemon a held item to advance by 3 (rarely by 4, but not sure when so be careful).
* Select one of your Pokemon **with 4 moves** and attempt to teach it a new move. Just before replacing an old move, press `B` to reject it **(don't actually teach the move)**.
This will cause 1 advancement. If you stay in the move replacement screen for too long, the Pokemon will blink causing another advance (helpful for 2 advances but be careful).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav6.png)

Considering you did everything right, your current Index value matches `Min Index` value (15 in my case) all you need to do now, 
is go to the **empty side of your bag** I recommended in the beginning of the guide, and wait until you get ~110-120 frames before your target (exiting the bag usually takes up to ~100 frames).

At this point, press `Start + Select` to freeze the game. If you do this at a non empty side of the bag, you will be prompted to sort the existing items with dire consequences.

Citra is not affected. You can pause wherever you want since the hotkey is not used elsewhere).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav7.png)

Decide the frame type (odd/even) you want to hit, and exit the bag at a frame of the same type. 
To do this, hold the right-back blue arrow icon, press `Select` 2 times and release, then press `Start` to unfreeze and exit the bag. 

When in the X menu, freeze the game again and keep tapping `Select` until reach **10** frames before your target.

Hold down `X` and tap `Select` 10 times to reach your target frame while closing the menu slowly.

Finally, using the Circle Pad, press `Select` 4 times to rotate the player character.

If everything done right, you will activate the patch at the expected tile (-5, 8 in my case) with the correct IVs and everything.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav9.png)

### Things to NEVER forget

* After finding the desired index, if you want a nice spread, don't forget to refresh the MT seed until you find it.
* When you have stood on your spot, make sure that your current step counter value is 19 (red marked). 
* The spot itself, requires background search. If there is an NPC next to the character, by pressing `A` when rotating, you may speak to them accidentaly. 
The same goes for spots where an item like a Route sign can be interacted or a water tile nearby which will prompt you to surf inside it.
* If you have used Pokemon Amie, make sure to turn it off when entering the bag. If it remains in queue, it will start advancing again like crazy when exiting.
* Exit the bag by pressing `B` to land in the menu. Pressing `X` instead, will get you to the overworld, and if the place is noisy, the NPC influence will take effect before you can even get control of your character.
* At noisy places, there is a slight chance that the resulting egg move will be wrong while everything else will be correct.
Apparently the NPC influence interrupts the DexNav generation and advances the prng state that decides the egg slot.
There is not much we can do about this, other than keep track of the NPCs advances, and let them do their thing before entering the bag.
If you feel like taking the risk and assuming an unexpected NPC blink will occur, you can check the `Alt Egg Move` box.

[Suggested ways to deal with unstable delays](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#unstable-delays)

[Info about Special Places](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#special-places)

[Practicing DexNav and Interesting facts - Conclusions](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#practicing)

