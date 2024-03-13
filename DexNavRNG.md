# DexNav RNG Abuse Guide

### Because PokeRadar shiny patch RNG was only the beginning!

Ever wanted to find a perfect 6IV shiny in the wild that has its hidden ability and an egg move it could not learn otherwise?

Follow this guide for **RNG abusing** DexNav mechanics and enjoy the full potential of this amazing ORAS exclusive feature!
A flawless Pokemon (shininess/stats/ability/egg move/gender/level) is an absolutely realistic target even without emulator usage.

If you want to catch easy and fast shinies without caring too much about stats and other traits, 
then [Normal Wild RNG guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md) may suit you better.
In any case though, I still recommend reading it before attempting DexNav, since it is the base for TinyMT RNG.

This guide will provide you with some useful tips to save time and effort but don't expect to succeed in just a few minutes without prior experience.

Note that, apart from fishing and Rock Smash exclusives, any other species that appears in the grass/water is available with this method.

### Tools needed
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder) (The most up to date build - The main tool for this RNG)
* [3DS RNG Tool fork](https://github.com/Bambo-Rambo/3DSRNGTool#forked-from-wwwwwwzx3dsrngtool) (This version has DexNav RNG implemented unlike the official version)
* [Pcalc G6](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) or [PokeReader](https://github.com/zaksabeast/PokeReader)
for **3ds** or [CitraRNG fork](https://github.com/Bambo-Rambo/CitraRNG) for **Citra Emulator**

### Recommended
* Max Repels
* A Pokemon with the synchronize ability if you want a specific nature
* If playing on console, it will be helpful to keep one side of the bag empty (we will see later why). I discarded all my Berries since I don't have any use of them

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav1.png)

# General Info

Despite the increased difficulty, the main advantage of DexNav RNG over Normal wild RNG 
(apart from the countless [extra benefits](https://bulbapedia.bulbagarden.net/wiki/DexNav#Special_qualities) and DexNav exclusive Pokemon)
is that, similarly to Pokeradar in XY, we can generate guaranteed **shiny patches**.

This means that IVs and shininess use separate prng states for determination, speeding up the process of finding high IV shinies a lot!

Even better, unlike Pokeradar, building a chain is not required (although it helps) for generating a shiny patch, so users may RNG for one immediately upon booting the game.
Here are some [more differences](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#differences-between-dexnav-and-pokeradar) between Pokeradar and DexNav to get the main idea.

Now most people including shiny hunters use the "Search function" in the touch screen to guarantee the desired species and avoid getting the wrong shiny.

Regarding RNG abuse though, this method is not always consistent because random NPC movements advance the TinyMT state unpredictably.

In this guide, we are going to abuse this 50% chance of "randomly" triggering a hidden Pokemon by moving (walking/turning) closely to the wild area.
The idea is to make **19 turns (or steps)**, do the necessary advances, wait, and finally **rotate** the character at the right time and succeed.
As said earlier, fishing exclusive Pokemon **do not** spawn with this method.

# Getting Started

### Step 1 – Choosing the target TinyMT Index in Tiny Finder

The **TinyMT prng state** determines slot (species), potential, shininess, HA, egg move, held item, nature sync and the possible (+10) level boost.

The **MT state** mainly determines the IV spread and gender.
However, if shiny, HA and synchronize checks, fail from TinyMT, MT will determine those values instead 
(not recommended, we will pull them from TinyMT no matter what, unless you don't care about them).

We are looking for a good TinyMT index first because the only way to get a new TinyMT seed, is by resetting the game.
When we find something that covers our expectations, we will focus on the MT seed which can be refreshed pretty quickly (takes around 5 seconds if you are using the NTR Helper).
We don't want to find a frame with a nice spread (MT) only to realize that there are no good TinyMT indexes to combine with.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#setting-up-tiny-finder) on how to setup Tiny Finder depending on your preferences,
as well as understand how the Search Level and Chain length affect the results.

When you are done, it's finally time to boot the game.

Connect your console **to 3DS RNG Tool first** then to Tiny Finder using the NTR Helper and when the [first cutscene](https://camo.githubusercontent.com/0ad13238fe4c81572505be45e2fc78cd864f9e0c5abf7ff3d1809d6da1bd23f0/68747470733a2f2f692e696d6775722e636f6d2f6c38534c4b62622e706e67) loads, 
press `Update` in Tiny Finder (this step is not necessary but is really helpful especially for beginners).

It will read your initial TinyMT state automaticaly, as well as your current step counter and the current chain length (both set to 0 when booting the game obviously)
and will then update the list with possible available results to choose from.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#dexnav-results) how to read the results from Tiny Finder.

If you didn't find what you were looking for, set the chain length to 4, **uncheck** the checkbox to prevent the tool from resetting it to 0, and press `Update` again.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav2.png)

A **4-length chain** takes 2-3 minutes to build and is totally worth it, unless you are looking for a low level Pokemon on purpose (so the +10 level boost should be avoided).

If you still didn't find the desired index, hard reset (or soft reset if using Pokereader) your system and try again.

### Step 2 – Choosing the target MT frame in 3DS RNG Tool
You have found what you were looking for, so it’s time to focus on the main frame and choose the IVs of your target. 

In 3DS RNG Tool, choose `DexNav` and set up the tool **according to your target index** in Tiny Finder.

**Important: It's impossible to advance more than 3 to 3,5 TinyMT indexes per frame so set the Min Frame to something HIGHER than (your target index / 3) to be sure. 
My target index is 41800 so I set the Min Frame to 20000 (41800 / 3 ≈ 13933).
More details in a bit.**

As shown in the previous image, the target index I am gonna aim for **in Tiny Finder**, guarantees shininess, has the Hidden Ability, 
successfuly syncs the Nature and has 3 perfect IVs (potential) so I need to set up 3DS RNG Tool like this:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav3.png)

If your target is Unown (Mirage Cave only), check the corresponding box to make it show the form/letter for each frame.

Note that the delay tends to be a bit **unstable** sometimes so it’s better to search for 3-5 consecutive identical frames (I take the risk here with 2).
This will also solve the odd/even frame issue.

You may now pick any frame of your choice. 

# In-game preparation

If you have filtered the results to the maximum, your target TinyMT index is most likely very far away and you will need to advance thousands of indexes.
The fastest way is going to a rainy place and wait there (Route 120 always works, just move down to the map a little and a heavy rain will start). 
You can also activate the Pokemon Amie function at the lower screen of your system.

* Rain advances by 3 indexes per frame advance
* Pokemon Amie advances by 0,5 indexes per frame advance (apparently doesn't work if you have interacted with strangers in the PSS)
* Combining these 2, results in advancements of 3,5 indexes per frame so you can approximately calculate how much time you need to stay there. Leaving a bit earlier is suggested so you won't miss your index.

In the following image, I make use of both.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav4.png)

When you get close to your target index, return to your location 
(If you have to build the 4-length chain, I suggest returning around ~1500 indexes before your target otherwise the suggested number is ~800).

Check the coordinates of your index in Tiny Finder and find an appropriate tile to stand on. 
Remember that the resulting patch must fit INSIDE the grass (or water if you aim for an aquatic encounter).

In any case, you should stand somewhere OUTSIDE of grass or water because moving inside them, causes (2) unwanted advancements (inevitable in caves).

Build up your chain if you have to (check [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#chain-building) how to build a successful DexNav chain without breaking it), 
stand on the correct spot, press `Update` to refresh the Step Counter and take the remaining steps/turns until it reaches 19.

### Finding the noise for your current spot

**Skip this step if you are sure there are not many NPCs in the area (most common scenario).**

When closing the X menu and the character is free to move again, 
the NPCs influence (blinking/moving) starts taking effect and we need to find out if this happens immediately after closing the menu, or a bit later in which case it won't be an issue.

For Normal Wild RNG, the tool takes that into account (since the suggested spots are predetermined), 
but since your position in DexNav RNG varies, you have to calculate the noise yourself (0 in most cases but still).

Press `X` to open the menu and then freeze the game by pressing `Start + Select`.

While the game is frozen, hold down `X` and tap `select` 10 times, in order to close the menu slowly.

If you notice the TinyMT state changing in the 10th press, take note of how much it advanced and set `Calibration` to that number.

# DexNav RNG

Let Poke – Amie and the NPC influence advance for you.

When you are about 50-55 indexes away (keep pressing `Update` to keep track of advances), **CLOSE POKE – AMIE** and enter the bag.

The TinyMT state **does not advance inside the bag** on its own, so we have full control now.

At this point also, Tiny Finder will have set the `Min Index` value to something, based on the selected location.
This is the number of advances consumed **upon exiting the bag** (you cannot hit anything lower) and we need to account for that 
(it's usually 15, sometimes 3 in caves etc but I recommend making a test for your current location/spot to be sure).

Just advance the TinyMT state until the value of your target index matches `Min Frame`.

Here are some simple and consistent ways to advance inside the bag:

* Turn on/off the EXP Share to advance by 3 * party number. If you have 5 Pokemon in your party for example, using the Exp Share, advances 3 * 5 = 15 indexes.
* Give your Pokemon a held item to advance by 3 (rarely by 4, but not sure when so be careful).
* Select one of your Pokemon **with 4 moves** and attempt to teach it a new move. Just before replacing an old move, press `B` to reject it **(don't actually teach the move)**.
This will cause 1 advancement. If you stay in the move replacement screen for too long, the Pokemon will blink causing another advance (helpful for 2 advances but be careful).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav6.png)

Considering you did everything right, your current Index value matches `Min Index` value (15 in Safari Zone) all you need to do now, 
is go to the **empty side of your bag** I recommended in the beginning of the guide, and wait until you get ~110-120 frames before your target (exiting the bag usually takes up to ~100 frames).

At this point, press `Start + Select` to freeze the game. If there is no empty side in the bag, you will be prompted to sort the existing items with dire consequences.

Citra is not affected. You can pause wherever you want since the hotkey is not used elsewhere.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav7.png)

Decide the frame type (odd/even) you want to hit, and exit the bag at a frame of the same type. 
To do this, hold the right-back blue arrow icon, press `Select` 2 times and release, then press `Start` to unfreeze and exit the bag. 

When in the X menu, freeze the game again and keep tapping `Select` until reach **10** frames before your target.

Hold down `X` and consume the remaining 10 frames by tapping `Select`. This will also close the menu slowly.

You are on your target frame and the player character is free to move again so, while moving the Circle Pad, 
press `Select` to advance 4 frames, release the Circle Pad and tap `A` to unfreeze and make the final movement.

If everything done right, you will activate the patch at the expected tile (-5, 8 in my case) with the correct IVs and everything.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNav9.png)

### Things to NEVER forget (from personal experience)

* If using Pokereader instead of Pcalc, frame advances require 1 `Select` press instead of 2.
* After finding the desired TinyMT index, don't forget to refresh the MT seed a few times in case you are looking for a nice spread.
* When you have found your spot, make sure that your current step counter value is 19 (red marked) before entering the bag. 
* If you have used Pokemon Amie, make sure it is turned off when entering the bag. If it remains in queue, it will start advancing again like crazy when exiting.
* When in the bag, exit by using the blue arrow in the touch screen of your system. Don't forget the odd/even issue.
* At noisy places, there is a slight chance that the resulting egg move will be wrong while everything else will be correct.
Apparently the NPC influence interrupts the DexNav generation and advances the prng state right before the egg slot determination.
There is not much we can do about this, other than keep track of the NPCs advances, and let them do their thing before entering the bag.
If you feel like taking the risk of assuming an unexpected NPC action, you can check the `Alt Egg Move` box.

[Suggested ways to deal with unstable delays](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#unstable-delays)

[Info about Special Places](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#special-places)

[Practicing DexNav and Interesting facts - Conclusions](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#practicing)

