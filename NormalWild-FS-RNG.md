# XY/ORAS wild Pokemon RNG made EASY

* Your 2ds/3ds system must run **[Custom Firmware (CFW)](https://3ds.hacks.guide/)** in order to follow this guide.
* This guide is about RNG abusing for **single** wild Pokemon. It **WORKS** with Friend Safari and it **WORKS** on Emulator too.
* If you want to RNG for **Horde encounters**, use this **[guide](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/HordeRNG.md)** instead.

### Tools needed:
* The latest commit of **[Tiny Finder](https://ci.appveyor.com/project/Bambo-Rambo/tinyfinder/build/artifacts)** (The .zip file)
* The latest release of **[3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases)** (The .exe file)
* The PokeReader plugin. This is the overlay that appears on screen and shows your current RNG info as well as wild Pokemon's stats.
  Use one of the following guides to download, install and activate PokeReader
   on your device: **[[3ds](https://www.pokemonrng.com/install-pokereader/)]** / **[[Emulator](https://www.pokemonrng.com/install-pokereader-emu/)]**

### Recommended to have in game
* Repels (100 steps)
* Having acquired the Exp. Share
* Having acquired the Shiny Charm if going for shinies
* A "Synchronizer" in the 1st slot of your party with the desired nature
* One completely empty side in the bag. I discarded all my berries since I don't need them

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild1.png)

### Introduction

In Gen 6 games, when using honey or sweet scent in most areas, hordes of 5 Pokemon appear instead of single ones,
which means we have to trigger the desired encounter by **moving in the grass**.

To do this, we are gonna abuse 2 RNG states (Initial Seeds) instead of 1: **MT** and **TinyMT**.

**MT** determines IVs, shininess (PID), gender and advances by 2 per frame or 60 per second.

**TinyMT** determines species, nature sync and most important, the successful (or not) trigger of the encounter.
It is more complicated than MT and is affected by multiple factors (NPC movements, character blinking etc) but we have an easy way to manipulate it.

### Logic

If you have RNG abused for Gen 7 eggs **without** using Masuda method and/or Shiny Charm, you already know that we manipulate the TinyMT
by rejecting/accepting eggs in order to reach the target egg frame first (which generates the desired stats, nature, gender and ability) and then, 
just before accepting the final egg, we wait until reach our shiny frame.

Gen 5 wild encounters is another example.
First we advance the IV frame by taking steps, and then use chatot pitches to advance the PID frame.

Similarly to these, we are gonna abuse MT and TinyMT simultaneously to hit our target.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild2.png)

As said above, MT advances constantly but TinyMT stops advancing inside the bag (unless we force it to), of which we are gonna take advantage.

### Preparation

Load the game and save in the appropriate spot for your location according to the following albums:

* [XY](https://imgur.com/a/pGk0bhM)
* [ORAS](https://imgur.com/a/B3URhjo)
  
Soft reset your game and stop in the following screen, which is when your Initial Seed is being determined:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild3.png)

Let's put it in 3DS RNG Tool and see what we can hit
(careful not to confuse MT with TinyMT seeds).

My target is Zoroark so I have to set the Gender Ratio to 7:1.
If you are using a synchronizer, check the **Assume synced** button and your synchronizer's nature in order to get accurate gender and nature results.
The rest should be self explanatory.

Press **Calculate** to get the results for your current seed.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild4.png)

If you are looking for a better IV spread or you get no results at all, 
press **B** on your 3ds to return to the previous cutscene.
Doing so, you reject the current Initial Seed, so press **A** to generate a new one.
Type the new seed in 3DS RNG Tool and press **Calculate** to get the new results.

Repeat this process until you find something that meets your preferences but don't have too high expectations.

When ready, press **Continue** on your 3ds to load your save file, use a repel and start walking around (running works but not recommended) until its effect ends.

**Do not step outside the encounter tiles.** 
Walk inside them, the repel protects you from random unwanted encounters anyway.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild5.png)

When the repel is consumed, don't use another one, enter the bag and press **Start + Select** to freeze the game
(if you get a random encounter for whatever reason, repeat the repel process).

Time to adjust Tiny Finder.

Input your **TinyMT Seed**.

Choose your location **first** (very important for accurate results) and **then** set **Min Index** to whatever your current **Advances** (not MT Advances) are.

Finally put the number of Pokemon in your party (3 in my case).
The rest should be self explanatory.

Press **Generate** and check the results.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild6.png)

Index 700 is the closest one so I am gonna aim for that.

### RNG

Right click on the row of your target index (700 in my case) and press **Calculate Advances**.

A small window will pop up with the instructions you need to follow.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild7.png)

If you get the message that no advances are required, you can skip to the next section **[Hitting the target Pokemon](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md#hitting-the-target-pokemon)**.

If your target index is unreachable due to it being too close, you will get the respective message.

Otherwise, you need to reach the number shown in the header I have marked in the image above (673 in my case).
This is because when you close the bag, 27 advances will be consumed so you need to stop earlier.

* Turning on/off the Exp. Share, advances the TinyMT
* Giving one of your Pokemon a new item to hold (even if it already holds something), advances the TinyMT
* Attempting to teach one of your Pokemon a new TM/HM move and then **reject it** (don't actually learn the move), advances the TinyMT

Each of these actions causes different (predictable) RNG jumps and the tool combines them to calculate the shortest path.

After following the indicated steps, I reach index 673 as expected.

The TinyMT part is done, so let's switch to our empty side of the bag and let the game advance MT frames on its own.

### Hitting the target Pokemon

According to 3DS RNG Tool, my target is 17873 so I will freeze the game **(Start + Select)** around 110 frames earlier.

At frame 17763, I hold **B** and press **Start** once to unfreeze the game while exiting the bag.

When the overworld is loaded, quickly freeze the game again **(Start + Select)**.

Spam **Select** presses until you get 10 MT frames before your target (17863 in my case).

Finally, hold **B** and tap Select **5 times**.

This will slowly close the X menu, while advancing to your target frame, everything is ready!

Hold down any arrow on the D-pad (except the one your character is looking at) and hold **A** to make a rotation and trigger the encounter.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild8.gif)

### Summary

* Waste a repel inside the wild area tiles.
* Enter the bag and let Tiny Finder create the best path from your current TinyMT advances to the target.
* Around 110-120 MT frames **before** your target, exit the bag, and manually advance until you are 10 frames away.
* Hold **B** and tap **Select** 5 times.
* Rotate the character and succeed.

### Ways to advance the TinyMT state fast
* If you can find rain somewhere, you will have huge advances per frame. In ORAS you can use the south part of Route 120. In XY, possible rainy places include: Routes 8, 14, 16, 19, Laverre City. 
* During wild battles at Route 17, there are big index jumps. Start a random wild battle and wait there until you get close. 
* Using Poke Amie in the lower (pink) screen also advances by 1 index per frame.
* At route 16, there are 2 roller skaters. Stand in front of them to block their way and you will have 1 advance per 2 frames.

### Notes
* The delay for 3DS RNG Tool in Kalos routes 9 and 17, is 20 instead of 6.
* Tiny Finder supposes that all NPCs in an area are active. 
If you fight one of them accidentaly, leave the area and return to reset their active state.
