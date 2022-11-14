# Normal Wild - Friend Safari RNG

### Tools needed:
* [3DS RNG Tool](https://ci.appveyor.com/project/Bambo-Rambo/3dsrngtool/build/artifacts)
* [Tiny Finder](https://ci.appveyor.com/project/Bambo-Rambo/tinyfinder/build/artifacts) (The latest commit)
* [Pcalc G6](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) (Retail) or [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) (Emulator)

### Recommended in game
* Repels
* Shiny Charm if going for shinies
* One completely empty side in the bag. I discarded all my berries since I don't need them

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild1.png)

### Introduction

In generation 6, when using honey or sweet scent in most areas, hordes are generated instead of single wild Pokemon.

This means that in order to abuse for single Pokemon in the wild, we have to trigger the desired encounter by moving in the grass.

The gender, IVs and shininess (PID) for wild encounters in gen 6 games, are generated from the initial seed (main state / MT).

The slot (species), nature sync and most important, the successful (or not) trigger of the encounter, are generated using a second state consisting of 4 hex numbers (TinyMT).

The 2 states need to be manipulated together in order to get the desired Pokemon (when reaching the target frame, your current index should generate the desired encounter).

The main state (MT) advances by 2 per frame or 60 per second, while TinyMT is more complicated and is affected by multiple factors 
(NPC movements, character blinking etc).

In the past, a special timeline was required to combine the 2 states and manipulate the final result.

But with this new method, all we gotta do, is deal with TinyMT alone first, 
and then wait and let the game run until we reach our target main frame to get the correct stats and shiny.

### Logic

Before proceeding to the main guide, it is important to explain how things work, and for that, 
I am gonna take gen 7 egg RNG as an example, which is similar and funnily enough, uses TinyMT as well.

If you have RNG abused for eggs **without** using Masuda method and/or Shiny Charm, you already know that, 
we keep rejecting/accepting eggs in order to reach the target egg frame first (which generates the desired stats, nature, gender and ability) and then, 
just before accepting the final egg, we wait until reach our shiny frame.

Gen 5 wild encounters is another example.
First we advance the IV frame by taking steps, and then use chatot pitches to advance the PID frame.

Similarly to these, for gen 6 wild RNG, we are going to do some specific actions in order to reach the appropriate TinyMT index first, which guarantees a successful encounter, 
the desired species and nature sync (optional), then we are gonna wait until reach our target main frame, for IVs and shininess, and finally trigger the encounter.

### Getting Started

Boot the game with Pcalc, connect your console to 3DS RNG Tool using the NTR Helper (see [here](https://github.com/wwwwwwzx/3DSRNGTool/wiki/NTR-Helper-Usage)) 
and keep reseeding until you find a nice spread (Press 'B' in the "Continue" screen, and then 'A' to generate a new seed).

The gender of the target Pokemon may be affected if you plan on syncing the nature, so if that's the case, check the "Assume synced" button in 3DS RNG Tool to get accurate results.

Connect with Tiny Finder as well (Generator -> Extra -> NTR Helper).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild2.png)

When in game, use a repel and start walking around (preferably inside the grass) until it is consumed.
Then stand in the recommended spot according to the following albums:
* [XY](https://imgur.com/a/pGk0bhM)
* [ORAS](https://imgur.com/a/B3URhjo)

You can't trigger encounters directly from booting the game so a few steps are required to get rid of that restriction (around 5 for grass/flowers and more for caves).

For consistency purposes, I always waste a whole repel.

If you accidentaly trigger a random encounter after the repel effects ends, use another one and repeat. 
When ready, freeze the game by pressing Start + Select.

In Tiny Finder, select the location (very important for accurate results) and you will notice that the min index value will be set to 
something between 3/15/27.
I will explain later why.

I will do the RNG in Pokemon Village's yellow flowers so min index was set to 27 automatically.

Finally, my target Pokemon is Zoroark so I select it in the filters along with the rest of my preferences (only sync in this case).

After pressing "Update" the tool will show all (yellow marked) indexes that trigger wild Zoroark encounters (slots 10, 11, 12).

Since index 46 is very close, I am gonna aim for that.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild3.png)

Enter the bag and press "Update" again.

27 is the number of TinyMT advances I will get, when I press 'B' to exit from the bag to the menu.

This means that if I enter the bag in Pokemon Village, I cannot hit anything less that index 27.

And the reason why we enter the bag in the first place, is because player blinks no longer happen 
and the TinyMT state freezes, so we have better control of it.

We are going to abuse this mechanic, in order to land on our target index directly from the bag.

### RNG

Now we know that the TinyMT state freezes inside the bag and doesn't advance until we manually do it ourselves.

The purpose is to advance until we are 27 indexes **before** our target index.

And here are some ways to do this inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 index (In fact what advances here, is checking the summary screen of the Pokemon). 
Teaching the move will advance more so you need to avoid it (If you stay in the summary screen for too long doing nothing, it will advance by 1 again - Pokemon blinks).
* Giving your Pokemon a held item, usually advances by 3 indexes (rarely by 4).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes.

When I entered the bag, the TinyMT also advanced by 1 index before freezing so the target index became 45.

45 - 27 = 18 so I need to advance 18 indexes inside the bag.

And since my party consists of 6 Pokemon (6 x 3 = 18), all I need to do now, is turn on the Exp Share once and I am done with the TinyMT part.

At this time I was really lucky but sometimes the target index may be far away.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md#ways-to-advance-the-tinymt-state-fast) on how to advance TinyMT indexes faster.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild4.png)

### Finalizing - Hitting the target Pokemon

Now I am 27 indexes away, which means that when I press **'B'** to exit the bag, I will land on my target index.

Stay in the empty side of the bag until you get close to your target main frame (the one you found earlier in 3DS RNG Tool).

Around ~110 frames before, press Start + Select to freeze the game.

Tap Start to unfreeze and then 'B' immediatly as fast as you can to exit to the menu.
(If you don't have an empty in your bag, avoid pressing Start/Select because you will be prompted by the game to sort the existing items).

It would be ideal to hold 'B' and tap Start to unfreeze, but Pcalc doesn't allow simultaneous use of the two buttons.

While exiting the bag, when the black screen goes away and the overworld is loaded again, freeze the game (Start + Select) and be careful not to miss your frame.

If everything done right, you landed on your target TinyMT index.

Now all you need to do is reach exactly 10 frames before your target so start spamming Select presses.

At 10 frames away, hold 'X' and start tapping Select carefully in order to slowly close the menu.

Do that 8 times and your current frame will be -2 from your target (the game is still frozen).

Hold an arrow from the D pad in a direction different to the one your character is looking and press 'A' to rotate the character and trigger the encounter.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/Wild/Wild5.gif)

### Summary

* Waste a repel to increase the chances of succeeding.
* Stay in the recommended spot and enter the bag.
* Inside the bag, advance until you are 'n' indexes away from your target. The value of 'n' varies depending on your location. Tiny Finder will set it automatically.
* When 'n' indexes and 110-120 frames **before** your target, press 'B' **(not 'X')** to exit the bag, and advance until you are 10 frames away.
* Hold 'X' and advance 8 (or 10) times using the Select button.
* Rotate the character and succeed.

### Ways to advance the TinyMT state fast
* If you can find rain somewhere, you will have huge advances per frame. In ORAS you can use the south part of Route 120. In XY, possible rainy places include: Routes 8, 14, 16, 19, Laverre City. 
* During wild battles at Route 17, there are big index jumps. Start a random wild battle and wait there until you get close. This is a consistent way in XY since rain is not guaranteed anywhere and Poke Amie doesn't always work (see below).
* Using Poke Amie in the lower (pink) screen also advances by 1 index per frame, but it breaks if you have communicated online with other users (more to say here).
* At route 16, there are 2 roller skaters. Stand in front of them to block their way and you will have 1 advance per 2 frames.

### Notes
* Inside the bag, frames advance 1 by 1 so the odd/even issue is not a thing.
After exiting the bag though, your frame type will be odd if you exited in an odd frame and vice versa.
This is controllable if the game is frozen when exiting, but since B and Select buttons cannot be pressed together, it is pretty much out of your control.
For this reason, the shiny charm is necessary if going for shinies because it gives 3 consecutive identical shiny frames, and thus solves the odd/even issue.
Alternatively, you can exit the bag by holding 'X' and tap Start to exit in the overworld (Only for quiet places and also +1 index advance. See below why).
* After exiting the bag, if you also close the 'X' menu, the lower screen functions (PSS, Poke Amie etc) are reloaded and they cause 1 TinyMT advance.
This occurs after 12 frames which would be enough to ruin everything. 
However, by unfreezing slowly using the D Pad + Select, let's say that this process is "postponed" for a few frames. 
For Kalos routes 9 and 17, hold the D Pad arrow until the encounter starts. The delay in those places is 20 instead of 6 so keep that in mind.
* Tiny Finder supposes that all NPCs in an area are active. 
If you fight one of them accidentaly, leave the area and return to reset their active state.
