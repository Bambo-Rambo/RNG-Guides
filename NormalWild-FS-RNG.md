# Normal Wild - Friend Safari RNG

### Tools needed:
* [3DS RNG Tool](https://github.com/wwwwwwzx/3DSRNGTool/releases)
* [Tiny Finder](https://github.com/Bambo-Rambo/TinyFinder#readme) (The latest build)
* [Pcalc G6](https://gbatemp.net/threads/pokecalcntr-for-gen-6-the-rng-tool-suite-for-the-3ds.473221/) (Retail) or [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) (Emulator)

### Recommended in game
* Repels
* Shiny Charm if going for shinies
* One completely empty side in the bag. I discarded all my berries since I don't need them

![](https://i.imgur.com/B19lgMa.png)

### Introduction

In generation 6, when using honey or sweet scent in most areas, hordes are generated instead of single wild Pokemon.

This means that for abusing single Pokemon in the wild, we have to trigger the desired encounter by moving in the grass.

The gender, IVs and shininess for wild encounters in gen 6 games, are generated using the initial seed (main state / MT).

The slot (species), nature sync and most important, the successful (or not) encounter trigger, are generated using a second state consisting of 4 hex numbers (TinyMT).

The 2 states need to be manipulated together in order to get the desired Pokemon (when reaching the target frame, your current index should generate the desired results).

The main state (MT) advances by 2 per frame or 60 per second, while TinyMT is more complicated and is affected by multiple factors 
(NPC movements, character blinking etc).

Until recently, a special timeline was required to combine the 2 states and match the main state with the TinyMT state.

But with this new method, all we gotta do, is deal with TinyMT alone first, and then wait until we reach our target main frame to get the correct stats and shiny.

### Logic

Before proceeding to the main guide, it is important to explain how things work, and for that, 
I am gonna take gen 7 egg RNG as an example, which is similar and funnily enough, uses TinyMT as well.

If you have RNG abused for eggs **without** using Masuda method and/or Shiny Charm, you already know that, 
we keep rejecting/accepting eggs in order to reach the target egg frame first (which generates the desired stats, nature, gender and ability) and then, 
just before accepting the final egg, we wait until reach our shiny frame.

Similarly to this, for gen 6 wild RNG, we are going to do some specific actions in order to reach the appropriate TinyMT index first, which guarantees a successful encounter, 
the desired species and nature sync (optional), then we are gonna wait until we reach our target main frame, for IVs and shininess, and finally trigger the encounter.

### Getting Started

Boot the game with Pcalc, connect your console to 3DS RNG Tool using the NTR Helper (see [here](https://github.com/wwwwwwzx/3DSRNGTool/wiki/NTR-Helper-Usage)) 
and keep reseeding until you find a nice spread (Press 'B' in the "Continue" screen, and then 'A' to generate a new seed).

The gender of the target Pokemon may be affected if you plan on syncing the nature, so if that's the case, check the "Assume synced" button in 3DS RNG Tool to get accurate results.

Connect with Tiny Finder as well (Generator -> Extra -> NTR Helper).

![](https://i.imgur.com/R1QI3Af.png)

When in game, use a repel and start walking around (preferably inside the grass) until it is consumed.
Then stand in the recommended spot according to the following albums:
* [XY](https://imgur.com/a/pGk0bhM)
* [ORAS](https://imgur.com/a/B3URhjo)

You can't trigger encounters directly from booting the game so a few steps are required to get rid of that restriction (around 5 for grass and more for caves).

For consistency purposes, I always waste a whole repel.

If you accidentaly trigger a random encounter after the repel effects ends, use another one and repeat. 
When ready, freeze the game by pressing Start + Select.

In Tiny Finder, select the location (very important for accurate results) or check the corresponding button (Cave / Long grass) if needed.

In the 2 albums above, there is also a number for every location (+3 /+15 /+27).
Set the "Min Index" value according to them, I will explain later why.
My location is Pokemon Village so I set it to 27.

Finally, fill in the filters of the 3rd box in Tiny Finder to search for your target and press "Update".

* [Gen 6 wild encounter slots](https://sites.google.com/site/pokemonslots/gen-vi)

All the following indexes generate successful (yellow marked) encounters with slots 10-12 which are Zoroarks in Pokemon Village.

Since index 46 is very close, I am gonna aim for that.

![](https://i.imgur.com/kUJ1nyd.png)

Enter the bag and press "Update" again.

27, which is the number I used for Min Index, is actually the number of TinyMT advances I will get, if I press 'B' to exit from the bag to the menu.

This number varies depending on the location, but is always the same for a given spot.

And since it is predictable, we are going to abuse it, in order to land on our target index directly from the bag.

### RNG

The TinyMT state freezes inside the bag and doesn't advance until we manually do it ourselves, so we have full control now.

Here are some ways to advance inside the bag:

* Attempting to teach one of your Pokemon a new move and reject it, advances by 1 index (In fact what advances here, is checking the summary screen of the Pokemon). 
Teaching the move will advance more so you need to avoid it (If you stay in the summary screen for too long doing nothing, it will advance by 1 again).
* Giving your Pokemon a held item, usually advances by 3 indexes (rarely by 4).
* Turning on/off the EXP Share advances by 3 * number of Party. This means that if you have 4 Pokemon in your party, using the Exp Share, will advance 3 * 4 = 12 indexes.

When I entered the bag, the TinyMT also advanced by 1 index before freezing so the target index became 45.

45 - 27 = 18 so I need to advance 18 indexes inside the bag.

And since my party consists of 6 Pokemon (6 x 3 = 18), all I need to do now, is turn on the Exp Share once and I am done with the TinyMT part.

At this time I was really lucky but sometimes the target index may be far away.

See [here](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/NormalWild-FS-RNG.md#ways-to-advance-the-tinymt-state-fast) on how to advance TinyMT indexes faster.

![](https://i.imgur.com/ovcPCW1.png)

### Finalizing - Hitting the target Pokemon

Now I am 27 indexes away, which means that when I press **'B'** to exit the bag, I will land on my target index.

Stay in the empty side of the bag until you get close to your target main frame.

Around ~110 frames before, press Start + Select to freeze the game.

Tap Start and then 'B' immediatly as fast as you can to exit to the menu.

It would be ideal to hold 'B' and tap Start to unfreeze, but Pcalc doesn't allow simultaneous use of the two buttons.

While exiting the bag, when the black screen goes away, freeze the game again and be careful not to miss your frame.

If everything done right, you landed on your target index.

Now all you need to do is reach exactly 10 frames before your target so start spamming Select presses.

At 10 frames away, hold 'X' and start tapping Select carefully in order to slowly close the menu.

Do that 8 times and your current frame will be -2 from your target (the game is still frozen).

Hold an arrow from the D pad in a direction different to the one your character is looking and press 'A' to rotate the character and trigger the encounter.

![](https://i.imgur.com/4VaKWy2.gif)

### Ways to advance the TinyMT state fast
* If you can find a rainy, place you will have huge advancements per frame. In ORAS you can use the south part of Route 120. In XY, possible rainy places include: Route 8, Route 16, Route 14, Route 19, Laverre City. 
* During wild battles at Route 17, huge advancements occur. Go there, start a random wild battle and wait until you get close. This is a consistent way in XY since rain is not guaranteed anywhere and Poke Amie doesn't always work (see below).
* Using Poke Amie in the lower (pink) screen also advances by 1 index per frame, but it breaks if you have communicated online with other users (unfinished).
* At route 16, there are 2 roller skaters. Stand in front of them to block their way and you will have 1 advance per 2 frames.

### Summary

* Waste a repel to increase the chances of succeeding.
* Stay in the recommended spot and enter the bag.
* Inside the bag, advance until you are 'n' indexes away from your target. The value of 'n' for every location can be found [here](https://imgur.com/a/pGk0bhM) for XY 
and [here](https://imgur.com/a/B3URhjo) for ORAS.
* When 'n' indexes and ~110 frames away from your targets, press 'B' to exit the bag, and advance until you are 10 frames away.
* Hold 'X' and advance 8 (or 10) times using the Select button.
* Rotate the character and succeed.

### Notes
* Inside the bag, frames advance 1 by 1 so the odd/even issue is not a thing.
After exiting the bag though, your frame type will be odd if you exited in an odd frame and vice versa.
This is controllable if the game is frozen when exiting, but since B and Select buttons cannot be pressed together, it is pretty much out of your control.
For this reason, the shiny charm is necessary if going for shinies because it gives 3 consecutive identical shiny frames, and thus solves the odd/even issue.
Alternatively, you can exit the bag by holding 'X' and tap Start to exit in the overworld (Only for quiet places and also +1 index advance. See below why).
* After exiting the bag, if you also close the 'X' menu, the lower screen functions (PSS, Poke Amie etc) are reloaded and they cause 1 TinyMT advance.
This occurs after 12 frames which would be enough to ruin everything. 
However, by unfreezing slowly using the D Pad + Select, let's say that this process is "postponed" for a few frames. 
This also the case for Route 9/17 even though I thought they were affected.
Hold the D Pad arrow until the encounter starts. The delay in those places is also 20 instead of 6 so keep that in mind.
* Tiny Finder supposes that all NPCs in an area are active. 
If you fight one of them accidentaly and stops moving afterwards, leave the area and return to enable them again.
