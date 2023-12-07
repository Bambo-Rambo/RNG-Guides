# DexNav extra Info

### Differences between DexNav and PokeRadar

* When using the PokeRadar, you have to stand in a grass tile for it to work. For DexNav, you can stand anywhere although for RNG purposes, we will actually be standing outside the grass. Also PokeRadar usually generates 5 patches (unless they don't fit in the wild area) while DexNav only 1.
* When using the PokeRadar, species is decided when chain = 0 and then locks until the chain breaks. With DexNav you have to RNG for the slot as well (at least that's the case with the moving method that we will be using).
* When using the PokeRadar, if chain > 0, you RNG for the shininess first by activating the device, then wait in front of the patch until you reach your target frame to RNG for stats. You also see the patch glowing most of the time. In DexNav, you RNG for everything at once. You don't see the patch glowing but you see it shaking the whole time as well the Pokemon's info when approaching.
* To get guaranteed IVs with PokeRadar, you have to slowly build the chain (max 60 for 3 perfect IVs), although shiny patches can be generated after chain is 1 or higher. With DexNav you can generate a 1-3IV shiny patch immediately.
* PokeRadar doesn't have exclusive Pokemon and you can't abuse for some extra nice traits like HA, Egg move, Level Boost. DexNav can get you any available Pokemon for a given location including fishing and Horde Pokemon (Search function only - not implemented in Tiny Finder).
* PokeRadar patch RNG is more forgiving. You can activate the Radar device directly from the bag with no frame pressure. Also your patches don't always have to fit inside the grass to get what you want. DexNav is way more strict. If the patch doesn't fit, the game advances the RNG multiple times attempting to find something that fits. This increases the delay (although it happens more when using the Search method), and of course makes you fail.

### Setting up Tiny Finder

**Second Tab (Settings)**

`Shiny Charm` should be obvious.

`Grass`, `Long Grass`, `Cave`, `Water` are all different types that affect the available species.
If you know a specific Pokemon is available in a given location but you don't see in the 3rd tab, 
it's most likely due to having selected the wrong type.
For example Tentacruel in Victory Road will be visible only when you select `Water` instead of `Cave`.

If using a flute (Black/White - affects the wild's Pokemon level) select it otherwise leave it as is.

Ignore the `Calibration` field for now, for caves it will be set to 2 automatically.

`Search Level` is the number of times you have encountered the target Pokemon (shown in the DexNav screen for each Pokemon - caps at 999). 
I recommend using [PKHex](https://projectpokemon.org/home/files/file/1-pkhex/) to set it to 999 for every Pokemon.

**Af for `Chain` (caps at 99 then resets to 0), it's important here to make a brief explanation of how the chain length affects the results:**

Starting at 4, and for every +5, the chances of getting a nice index, greatly increase.
This means that if your current chain length matches one of the following numbers: [4, 9, 14, 19, 24, 29 etc], you are more likely to find what you are looking for.
In that case, your target Pokemon is also guaranteed to have the following:
* Egg Move
* A +10 Level Boost
* At least 1 perfect IV

(Chain = 49 gives even better results while 99 is the best possible value, but nobody is willing to build such a long chain)

Of course shininess is affected in a positive way as well.

Also starting at 0, and for every +5 added, [5, 10, 15, 20, 25 etc] the target Pokemon is guaranteed to have a +1 boost to its level. 
This doesn't affect the standar +10 that you may get. In fact, they can be combined resulting in a possible +29 Level Boost when the chain length tops at 99).

**Third Tab (Preferences)**

Select the desired species in the first combobox. 
The corresponding slot(s) will be auto selected, 
though you can still edit them manually (not recommended unless you are looking for more than 2 Pokemon).

In the third combobox, fill in the rest of the filters to your preference.

`Shiny` is searching for guaranteed shiny patches only (The main reason to select DexNav RNG in the first place).

`HA` for Hidden Ability and `Egg move` for an exclusive breeding move than cannot be obtained otherwise.

`Level Boost` is for getting a +10 boost to the wild's Pokemon level (an exclamation mark will be shown in the console's lower screen when occurs).

Finally, `Potential`, is the guaranteed perfect IVs you will get for that index (caps at 3). 
Leave it to 0 if you don’t care.

### DexNav results

The `Right` and `Up` columns show the coordinates of the generated patch. Negative values, mean opposite direction 
so for example a pair of Right = -5 and Up = 8, means that you will be getting a patch 5 tiles **left** and 8 **up** from the position you will be standing at.
If there is no grass/water tile in the indicative coordinates, you will fail your target so be careful when choosing your spot.

Yellow marked rows mean that a Pokemon will spawn successfully, otherwise they will be white (Clicking `Generate` will only show successful ones).

Egg moves that can only be learned by breeding will be marked in **bold**, while grayed out moves can be learned in one (or more) of the following ways:
* Leveling up
* TM/HM
* Move tutor
* Move relearner

Sync, Slot, Species, Level, HA and columns need no further explanation at this point.

`Shiny` when true, means forced shiny patch. 
The row will be marked as blue only if the patch is BOTH shiny forced AND successful, otherwise will still remain white.

`Potential` was explained above.

### Chain Building

To build a DexNav chain, all you need to do is defeat or capture Hidden Pokemon.

They don't have to be DexNav exclusives like Lillipup or Zorua, they can be Zigzagoon, Poochyena etc but they have to be hidden encounters.

This means that running around without repels to trigger a wild encounter by moving in the grass, does **NOT** work and will break the chain.

Run around (or use the search function in the lower screen), to trigger a DexNav shaking patch.

Use a repel to prevent wild encounters and approach the Pokemon slowly using the Circle Pad then either capture or defeat it.

The chain length value has now increased by 1.

Things that will break the chain include:

* Not encountering the hidden Pokemon that has appeared in the overworld either by leaving the area / waiting too long until it disappears / scaring it by running/walking fast towards it
* Running away from the battle

If you use the Search button to scan for hidden Pokemon and nothing is found, the chain does **NOT** break so you don't have to worry about this.

### Unstable delays

The delay can be affected by the current's system performance. I have noticed that I get less stable delays when I use the rain at Route 120 to advance fast. 
The 2 following ways can be seen as a workaround to deal with that:

* When reseeding for a specific spread, aim for 2-3 or more consequitive identical frames.
I suggest at least 2 in order to solve the odd/even issue while 3 can deal with the instability.

* As I said, the general system's performance affects the delay.
What I tried, was turn on the 2 Pcalc overlays (frame info and wild stats) around 2000 frames before exiting the bag and keep them visible until I rotate the character.
I noticed that this always gives me stable delays for quiet places with no NPCs (even if I have used the rain earlier).
Noisy ones may not be stable because extra advances caused by the NPC influence, might affect the performance.

### Special Places

Places that have no grass behave differently. 
These include caves, water routes, places like Sky Pillar, Mt Pyre inside, Route 111 etc 
and the advances by exiting the bag for them [are usually 3](https://imgur.com/a/B3URhjo).

For the most part, they can trigger random wild encounters by moving, almost everywhere. 

* If your current spot can trigger a wild encounter (regardless of whether you have an active repel or not), when moving, 2 rng advances may occur. 
This means that you need to set the `Calibration` to 2 (auto set in caves) in order to get accurate results.
For example, when you want to generate a DexNav patch in a water route, if your current spot is land, you don't need to edit the Calibration, 
otherwise, if your current spot is inside the water, you may need to increase it by 2. 
This is not always the case and you need to test yourself depending on your exact tile on the map.

* In grassy areas, we saw that the possilbe ring inside where a patch can be generated, is [-9, 9] for both vertical and horizontal. 
This is not the case with special places, where the ring, is apparently affected by your exact tile on the map and may be smaller than [-9, 9] (needs more research).
Generally speaking, I succeeded more frequently, by aiming for indexes whose coordinates are close to 0 for either the X or Y axis.
For example, indexes like [-7, 1] or [0, 8], are safer than [9 ,5] or [-6, 7].
If you have setup Citra, you can try multiple indexes quickly using the Date Searcher, until you find a successful one.
If you want to do this on 3ds, you should check the coordinates of your target index, 
and use the Date Searcher in order to find similar indexes with the same coordinates and test them on Citra.
If they are successful, you have high chances of succeeding on 3ds as well.
In terms of difficulty, from the easiest to the hardest ones: (long) grass << water routes < buildings < caves < route 111 desert

* The hidden Pokemon does not stay in the same spot but instead keeps moving constantly inside a new, specific ring. It also disapperars way easier especially if it can't move inside the ring due to your character's presence. Don't even try to build a chain in those areas. At chain 4, the Pokemon shakes literally 3 times before disappearing and you don't have enough time to approach it anyway. For whatever reason, GF decided to make this completely unfair.

### Practicing

The best places for practice, are Mirage Spots (except caves).
They are quiet places with no NPCs, the bag advances are the standar +15 and they include large grass tables which provide the user with a lot of possible tiles to stand on.
Also they don't have DexNav exclusive Pokemon making the rest of the slots more likely to appear.

Practice, practice, practice.
Keep aiming for non shiny indexes and try to hit them. Play around with the Pcalc menus to increase/decrease the lag and use whatever works better for you.

On 3ds you can use the NTR Helper to keep track of the steps and chain length.

On Citra you can find great and early indexes easily without the need to build a chain.

Try everything that you may find useful.

### Conclusions

* Depending on what the user is looking for, this can be either harder or easier than Normal Wild RNG but generally speaking, DexNav RNG is more challenging. While you have a higher chance of triggering a patch (50% unlike 13% and 7% for wild), you also have to deal with higher delay which boosts the NPC influence. Apart from that, if you choose to rotate and not step, you have to single tap the arrow which requires precision. Normal wild is easier on this part because you can just hold down the arrow and the encounter won't be affected. As for indexes, full DexNav ones are more rare of course, but with Tiny Finder filtering the results, this is not really an issue (Don't forget the Date searcher for Citra also). Finally the slot generation is an interesting topic. Their rarity is reversed on DexNav, making slot 12 the most common, slot 11 less common etc. GF probably wanted to give users an alternative and easier way to find those 1-5% targets faster.

* Unlike a possible search method that may exist in the future, this method gives full control of almost everything. Consistency is the key, and if you want a specific flawless Pokemon, you need to have control of both RNG states (MT and TinyMT). Citra allows for more possibilities, but 3ds is most likely to remain in this state.

