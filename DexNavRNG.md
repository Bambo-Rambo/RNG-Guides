# DexNav RNG Abuse Guide

### **Because PokeRadar patch RNG was only the beginning!**

After almost 7 years since ORAS came out, it's finally time to officially release 
the tool and the method to manipulate the trickiest of the encounters in generation 6 games.

Abusing the DexNav mechanics, has always been a cool way to obtain unique Pokemon which can have a random egg move (if not genderless), the Hidden Ability (if exists), 
up to 3 perfect guaranteed IVs, a boost to the level, while some Pokemon outside of the Hoenn Pokedex, cannot be obtained otherwise.

The most impressive feature of DexNav however, is that similarly to PokeRadar in XY games, 
special patches can be generated that result in guaranteed (square) shiny Pokemon.

Now imagine a forced shiny encounter with 3 perfect IVs and all the above.
Really powerful and one of its kind, but also complicated to perform, so having some experience with TinyMT RNG is required.

Please note that the exact egg move - and in some cases - the exact level of the resulting Pokemon cannot be predicted accurately.
The same goes for the held item.
We can still abuse for an egg move but we can't choose it, while the level is a bit messy but the species is not affected.

Also the following method doesn't work for species that can be obtained from fishing or hordes, although DexNav allows it generally.

This guide attempts to give some useful tips to save time and effort but don't expect to succeed without practicing.

I will also be using Hyperlinks with extra useful info, because I don't want to overfill the core of the guide. 
It is suggested not to ignore them.

### Tools you will need
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder/releases) (The latest release - The main tool for this purpose)
* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases) (For calibration and IVs)
* [Pcalc G6](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) for 3ds or [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) for Citra Emulator

### Recommended
* Max Repels
* Leading with a synchronizer if you want a specific nature
* [Slots for DexNav exclusive encounters](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#dexnav-slots).
* If on 3ds, it will be helpful to keep one side of the bag empty (We will see later why). I discarded all my Berries since I don't have any use of them

![](https://i.imgur.com/SOtYzzg.png)

# Introduction

Before starting, you may want to take a look at some [differences](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#differences-between-dexnav-and-pokeradar) between PokeRadar and DexNav to get the main idea.

As for the DexNav method itself, there are 2 ways of triggering a hidden encounter:

The first - which will be used in this guide - is the turn method.

Every 20 steps/turns, and if there is not already an active patch shaking in the overworld, there is a 50% chance of triggering one.
The idea is to make 19 turns (or steps), calibrate/manipulate the RNG, and in the 20th, rotate the character and succeed.

The second is using the "Search" function in the lower screen. While this method guarantees the species, and has a higher success ratio in some circumstances, 
it's totally not recommended for a number of reasons. 
The main issue is that it takes 2-3 seconds to generate the Pokemon and thus, a lot of things can be messed up during that time namely the delay and of course 
the TinyMT rng state which must be fully controllable but here instead, is affected by the random NPC movements in most areas.

Tiny Finder currently supports only the former while researches are being done for the latter as well.

# Getting Started

### Step 1 – Choosing the target Index

We give priority to the target index since it cannot be reseeded for, unless you hard reset your system.

We will be reseeding for the main frame afterwards because we don't want to find a nice spread only to realize that we don't have a nice index to combine with.

On how to setup Tiny Finder depending on your preferences, please see [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#tiny-finder-controls).

When you have setup the tool it's time to search, so boot the game.

If on 3ds, connect your console **to 3DS RNG Tool first** then to Tiny Finder using the NTR Helper and when you reach the first cutscene, press “Update” in Tiny Finder.
It will read your initial TinyMT state automaticaly, as well as your current step counter and the current chain length (both set to 0 when booting the game obviously).
It will then update the list with possible available results to choose from.

If you are doing this on Citra, use the “Date Searcher“ Tab to find the desired index way immediately and early.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#dexnav-results) how to read the results from Tiny Finder.

**(It's important here to make a brief explanation of how the chain length affects the results:**

Starting at -1, and for every +5, the chances of getting a nice index, greatly increase.
This means that if your current chain length matches one of the following numbers: [4, 9, 14, 19, 24, 29 etc], you are more likely to find what you are looking for.
In that case, your target Pokemon is also guaranteed to have the following:
* Egg Move
* A +10 Level Boost
* At least 1 perfect guarananteed IV

(Chain = 49 gives even better results while 99 is the best possible value, but nobody is willing to build such a long chain)

Of course shininess is affected in a positive way as well.

Also starting at 0, and for every +5 added, [5, 10, 15, 20, 25 etc] the target Pokemon is guaranteed to have a +1 boost to its level. 
This doesn't affect the standar +10 that you may get. In fact, they can be combined resulting in a possible +30 Level Boost when the chain length tops at 100).

For what described above, the optimal chain length number is 4.
Takes 2-3 minutes to build and is totally worth it unless you are looking for a low level Pokemon so the +10 boost should be avoided.

By the way, as I said earlier, when booting the game, the chain length value is by default 0 so pressing “Update” will set it to zero again.
To check the possible results for a given chain value, set it manually to the tool and press “Search” instead of “Update”.

If you still didn't find the desired index, hard reset your system and try again.

![](https://i.imgur.com/s6uOegk.png)

### Important

If you want to do this in noisy areas, you need to check in 3DS RNG Tool if your target index is hittable. 
Due to Blink(+2) advances, half of the indexes are not, so you need to check beforehand.
In the following image, index 45 is not hittable, and cannot be reached so I ignore it. 
Also index 46 should be avoided as well since it only lasts for 12 frames.

This is not the case with quiet areas where you may choose any index and we will see later how to hit it.

![](https://i.imgur.com/y9QfEqq.png)

### Step 2 – Choosing the target frame
You have found an index that satisfies you, so it’s time to focus on the main frame and choose the IVs for your target. 
Now 3DS RNG Tool doesn’t have an option for the DexNav in the main window but we will be using the “Poke Radar” method to predict the results.

Change the game version to either X or Y in the main window of 3DS RNG Tool to make the “Poke Radar” category appear. 
If you are aiming for a forced shiny index, set the delay to +14 otherwise set it to +16.
Note that the delay tends to be a bit unstable sometimes so it’s better to search for 3-5 consecutive identical frames.
This will also solve the odd/even frame issue.

Depending on the Potential of your target index, set the “Chain Length” value in 3DS RNG Tool as following:
* 1-19 if Potential = 0
* 20-39 if Potential = 1
* 40-59 if Potential = 2
* 60-100 if Potential = 3

You may now pick any frame of your choice. 

![](https://i.imgur.com/oZjjkQ3.png)


# DexNav RNG

Unlike Normal Wild (+6) which works fine, the delay here is higher (+14/+16/+18) so the NPCs have actually enough time to mess with your setup.
For this reason, we need to separate the 2 methods: the “noisy” and the “quiet”.

If your location is noisy, you will have to match your target frame inside your index. 
At this time I will not explain how to do that, because it’s basic TinyMT knowledge that you are supposed to have already and also because I want to focus on an easier method.

With that out of the way, we finally may begin.

If you have filtered the results to the maximum, your target index is most likely very far away and you will need to advance thousands of indexes.
The fastest way, is to fly to a rainy place (Route 120 works, just move down to the map a little and a heavy rain will start). 
Also you can activate the Pokemon Amie function at the lower screen of your system 
(doesn’t work if you have used it in the past, works only if you have just activated it).

* Rain advances by 3 indexes per frame (or by 6 per odd/even advance)
* Pokemon Amie advances by 0,5 index per frame (or by 1 per odd/even advance)
* Combining these 2, results in advancements of 3,5 indexes per frame so you can approximately calculate how much time you need to stay there. Leaving a bit earlier is suggested so you won't miss your index.

In the following image, I make use of both.

![](https://i.imgur.com/b1Q7r8z.png)

When you get close to your target index, return and build the chain if you have to.

Check [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#chain-build) to read how to build a successful DexNav chain without breaking it.

(If you don't need to build a chain, I suggest returning around ~800 indexes before your target. If you will be building a chain, the suggested number is ~1500).

When you are done with the chains, check the coordinates of your index in Tiny Finder and find an appropriate tile to stand on. 
Remember that the resulting patch must fit INSIDE the grass (or water if you aim for an aquatic encounter).

In any case, you should stand somewhere OUTSIDE of grass or water because when turning inside any of these, causes unwanted advancements.

Press the Update button to refresh the Step Counter, make the remaining steps/turns until it reaches 19 (will be marked as red in that case)
and once again make sure you are on the right spot.

Use the Poke – Amie again to get closer to your target index. 

When you are about 50-55 indexes away, CLOSE POKE – AMIE and enter the bag (The TinyMT state advances once when entering and then freezes).

In ORAS games, pressing the ‘X’ button to exit the bag, advances the TinyMT by 15 states, 
+1 extra advancement when the lower screen menus are reloaded so 16 in total (27 + 1 for XY if matters).

Since the numbers are predictable, we will be abusing them to avoid the process of matching the target frame with the index (the whole timeline calibration to be exact).
(The idea is to stay inside the bag until you get close to your target MAIN frame and then exit so you can land to your target index as well).

For what described above, the last thing to do, is advance inside the bag until you are 16 indexes away.

(Please note that some places like Mt. Pyre summit, advance 17 indexes instead of 16. Make a test for your location to be sure)

Here are some simple ways to advance slowly inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 (In fact what advances here, is checking the summary screen of the Pokemon). 
Don’t actually teach the move otherwise it will advance more.
* Giving your Pokemon a held item, usually advances by 3. (Rarely by 4, not sure when).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes etc
Now that you are 16 indexes away, all you need to do is wait until you get ~100 frames before your target.
The bag takes an inconsistent number of frames to close, but exiting 100 frames earlier, always works for me.

Note that inside the bag, the frames advance 1 by 1 instead of 2 by 2 and the frame type (odd/even) you will be at, is the one you were when exited. (The opposite goes for Citra).
This means that if your target frame is 22791, you need to exit the bag at an odd frame (22691 in my case).

I also mentioned in the beginning that you should have a side of your bag empty.
This is neccessary because when an item is highlighted, pressing either start or select, or both to pause, prompts you to sort the item list.

If there are no items though, you can pause without any trouble which is what I am doing here in the Berry List.

(Or you can use the Party instead of the bag but you won't have the Exp Share to advance faster. 

Citra is not affected. You can pause wherever you want since the hotkey is not used elsewhere).

![](https://i.imgur.com/b9u8WPz.png)

Exit the bag by pressing ‘X’ (not ‘B’), freeze the game, and keep tapping select until you reach your target frame.

All you need to do now, is rotate your character (stepping has a different delay, around 22 – not recommended).

Note that when rotating, you should not take an extra step to the new direction because this will result in hitting a later index.

This is a bit difficult to do precisely on console because you need to press ‘A’ instead of “Select” to make it work, 
but what helps me a lot, is abuse the Pcalc lag by having the stats menu (Start + Left) open as well (in fact that's the reason why I had them both open in the bag).

In any case it requires practice.

If everything done right, you will activate the patch at the expected tile (8, -6 in my case) and all you need to now is approach slowly and start the encounter.

![](https://i.imgur.com/Q1VLK4e.png)

![](https://i.imgur.com/0xRWZcj.png)

### Things to NEVER forget

* As said earlier, for noisy places you need to make sure that your target index is reachable. The bag method is very incosistent in that case so you 're gonna have to do the whole process the classic old way.
* The spot you will be standing on when triggering the patch, requires background search. If there is an NPC next to the character, when pressing "A" to rotate, you may speak to them accidentaly. The same goes for spots where an item can be interacted like a Route sign or a water tile nearby which will prompt you to surf inside it.
* When you have stood on your spot, make sure that your current step counter value is 19. If neccessary, rotate the character as much as needed.
* If you have used Pokemon Amie, make sure to turn it off when entering the bag. If it remains in queue, it will start advancing again like crazy when exiting.
* Close the bag at an odd frame number if your target frame is odd and vice versa. If you are using your party instead, do the opposite.
* Sometimes after tracking down the target index, I forget to reseed for a nice spread.

[Info about Noisy Places](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#noisy-places)

[Info about Special Places](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#special-places-caves-water-route-111-desert)

[Practicing DexNav and Interesting facts - Conclusions](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/ExtraInfo.md#practicing)

