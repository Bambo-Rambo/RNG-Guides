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
For example Tentacruel in Victory Road will be visible only when `Water` is selected instead of `Cave`.

If using a flute (Black/White - affects the wild's Pokemon level) select it otherwise leave it as is.

Ignore the `Calibration` field for now, for caves it will be set to 2 automatically.

`Search Level` is the number of times you have encountered the target Pokemon (shown in the DexNav screen for each Pokemon - caps at 999). 
I recommend using [PKHex](https://projectpokemon.org/home/files/file/1-pkhex/) to set it to 999 for every Pokemon.

**Af for `Chain` (caps at 99 then resets to 0), it's important here to make a brief explanation of how the chain length affects the results:**

When `(chain length + 1) mod 5 == 0`, the chances of getting a nice index, greatly increase.
This means that if your current chain length matches one of the following numbers: [4, 9, 14, 19, 24, 29 etc], you are more likely to find what you are looking for.
For reference, these are the benefits:
* **4** more shiny checks (**9** more if chain = 49, **14** more if chain = 99)
* Guaranteed to have an Egg Move
* A +10 Level Boost
* At least 1 perfect IV

Also, when `(chain length) mod 5 == 0` [5, 10, 15, 20, 25 etc], the target Pokemon is guaranteed to have a +1 boost to its level. 
This doesn't affect the standar +10 that you may get. In fact, they can be combined together resulting in a possible +29 Level Boost when the chain length tops at 99).

Chain 4 is the recommended value in order to save time while also increasing the odds a lot.

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

Yellow marked rows mean that a Pokemon will spawn successfully (Clicking `Generate` will only show these).

Egg moves that can only be learned by breeding will be marked in **bold**, while grayed out moves are the ones that can be learned in one (or more) of the following ways:
* Leveling up
* TM/HM
* Move tutor
* Move relearner

`Sync`, `Slot`, `Species`, `Level`, `HA` and `Potential` columns need no further explanation at this point.

Blue marked rows indicate a forced shiny patch!

### Chain Building

To build a DexNav chain, all you need to do is defeat or capture **Hidden Pokemon**.

They don't have to be DexNav exclusives like Lillipup or Zorua, they can be Zigzagoon, Poochyena etc but they have to be hidden encounters.

This means that running around without repels to trigger a wild encounter by moving in the grass, does **NOT** work and will break the chain.

Run around (or use the search function in the lower screen), to trigger shaking patches.

Use a repel to prevent wild encounters and approach the Pokemon slowly using the Circle Pad then capture/defeat it.

The chain length value has now increased by 1.

Things that will break the chain include:

* Not encountering the hidden Pokemon that has appeared in the overworld either by leaving the area / waiting too long until it disappears / scaring it by running/walking fast towards it
* Running away from the battle

If you use the Search button to scan for hidden Pokemon and nothing is found, the chain does **NOT** break so you don't have to worry about this.

### Unstable delays

The delay can be affected by the current's system performance. 
I have noticed that I get less stable delays when I use the rain at Route 120 to advance fast but here are 2 ways to deal with that:

* When reseeding for a specific spread, aim for 3-5 consequitive identical frames.

* As I said, the system's performance affects the delay.
What I tried, was turn on the 2 Pcalc overlays (frame info and wild stats) around 2000 frames before exiting the bag and keep them visible until the patch spawns.
I noticed that this always gives me stable delays for quiet places with no NPCs (even if I have used the rain earlier).
but noisy ones may not be stable because extra advances caused by the NPC influence, might affect the performance.

### Special Places

Wild areas with no grass at all, include: caves, water routes, buildings (Sky Pillar, Mt Pyre inside etc), Route 111 desert, and more.

Since there is no grass, wild encounters may be triggered pretty much anywhere inside the map, 
and the resulting hidden Pokemon will shift between adjacent tiles constantly rather than shaking within a single tile.

Under these conditions, there are some things to keep in mind:
* Moving (stepping/turning) within the wild area, advances the TinyMT state twice (regardless of whether a repel is active or not).
You can either aim for 2 indexes earlier, or just increase the `Calibration` by 2 (Tiny Finder will auto set it to 2 for caves).
Be careful though because not all tiles of such a place can trigger wild encounters.
Water routes as well as Shoal Cave (Low tide), Meteor Falls, Route 111 etc have tiles that are *encounter-free*
(quite easy to detect visually or you can check them manually by trying to use honey).

* Absolutely avoid building a chain to take advantage of what I described earlier.
The hidden Pokemon will shake literally 3 times before disappearing and you won't have enough time to approach it. For whatever reason, GF decided to make this completely unfair.

* The spot you will be standing on when doing the RNG, matters even more now.
The generated patch not only has to spawn in a *encounter-triggering tile*,
but the hidden Pokemon also requires additional space to move across the other 2-3 adjacent tiles.
Of course this may not always be easy, especially in narrow places like Rusturf Tunnel, Granite Cave etc.
Here is an example in Meteor Falls showing a good and a bad spot to stand on, if the patch were to spawn 7 tiles to the left and 0 tiles upward:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNavGood.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/DexNav/DexNavBad.png)
  
### Practicing

The best places for practice, are Mirage Spots (except caves).
They are quiet places with no NPCs, the bag advances are the standar +15 and they include large grassy terrains making it easy to find a spot that works.
Also they don't have DexNav exclusive Pokemon making the rest of the slots more likely to appear.

Practice, practice, practice.
Keep aiming for non shiny indexes and try to hit them. Play around with the Pcalc menus to increase/decrease the lag and use whatever works better for you.

On 3ds you can use the NTR Helper to keep track of the step counter and chain length.

On Citra you can even resuse the same state multiple times simply by resetting the game on the same date.

### Conclusions

* Depending on what the user is looking for, this can be either harder or easier than Normal Wild RNG but generally speaking, DexNav RNG is more challenging. While you have a higher chance of triggering a shaking patch (50% unlike 13% and 7% for wild), you also have to deal with higher delay which boosts the NPC influence. As for indexes, full DexNav ones are more rare of course, but with Tiny Finder filtering the results, this is not really an issue. Finally the slot generation is an interesting topic. The rarity is reversed on DexNav, making slot 12 the most common, slot 11 less common etc. GF probably wanted to give users an alternative and easier way of finding those 5% slots faster.

* Unlike a possible search method that may exist in the future, this method gives full control of almost everything. Consistency is the key, and if you want a specific flawless Pokemon, you need to have control of both RNG states (MT and TinyMT). Citra allows for more possibilities, but 3ds is most likely to remain in this state.

