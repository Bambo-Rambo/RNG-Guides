# DexNav extra Info

### DexNav slots

** These have been implemented in Tiny Finder already, but I still put them here just in case.

| Location  | Slot 1 | Slot 2  | Slot 3 |
| ------------- | ------------- | ------------- | ------------- |
| Route 101  | Lillipup  | Zorua  | Sewaddle  |
| Route 102  | Lillipup  | Gothita  | Tympole  |
| Route 103  | Lillipup  | Chatot  | Shellos  |
| Route 104 South | Pidove  | Chatot| Sewaddle  |
| Petalburg Woods  | Cottonee  | Paras  | Phantump  |
| Route 104 North | Pidove  | Sewaddle  | Chatot  |
| Route 105  | Frillish  | Skrelp (OR) / Clauncher (AS)  | Krabby  |
| Granite Cave  | Timburr  | Axew  | Onix  |
| Route 106  | Frillish  | Skrelp (OR) / Clauncher (AS)  | Krabby  |
| Route 107  | Frillish  | Skrelp (OR) / Clauncher (AS)  | Krabby  |
| Route 108  | Frillish  | Skrelp (OR) / Clauncher (AS)  | Krabby  |
| Route 109  |  Frillish  | Skrelp (OR) / Clauncher (AS)  | Krabby  |
| Route 110  | Trubbish  | Chatot  | Shellos  |
| Route 111  | Sandile  | Dwebble  | Gible  |
| Route 112 North | Ponyta  | Throh (OR) / Sawk (AS)  | Tyrogue  |
| Fiery Path  | Roggenrola  | Digglet  | Tyrogue  |
| Jagged Pass  | Ponyta  | Mankey  | Tyrogue  |
| Route 113  | Scraggy  | Klefki  | Bouffalant  |
| Route 114  | Skorupi  | Misdreavus  | Tympole  |
| Meteor Falls  | Deino  | Druddigon  | Clefairy  |
| Route 115  | Pidove  | Misdreavus  | Clefairy  |
| Route 116  | Pidove  | Joltik  |  Eevee  |
| Route 117  | Rattata  | Deerling  | Tympole  |
| Route 118  | Raticate  | Luxio  | Aipom  |
| Safari Zone  | Kakuna  | Buneary  | Pidgeotto  |
| Route 121  | Elgyem  | Hypno  | Aipom  |
| Route 122  | Frillish  | Finneon  | Alomomola  |
| Mt Pyre (Outside)  | Elgyem  | Bronzor  | Growlithe  |
| Route 123  | Frillish  | Finneon  | Alomomola  |
| Route 124  | Frillish  | Finneon  | Alomomola  |
| Route 125  | Frillish  | Finneon  | Seel  |
| Shoal Cave  | Cubchoo  | Delibird    | Dewgong  |
| Route 126  | Frillish  | Finneon  | Alomomola  |
| Route 127  | Frillish  | Finneon  | Alomomola  |
| Route 128  | Frillish  | Finneon  | Alomomola  |
| Route 129  | Frillish  | Finneon  | Alomomola  |
| Route 130  | Frillish  | Finneon  | Alomomola  |
| Route 131  | Frillish  | Finneon  | Alomomola  |
| Route 132  | Frillish  | Finneon  | Alomomola  |
| Route 133  | Frillish  | Finneon  | Alomomola  |
| Route 134  | Frillish  | Finneon  | Alomomola  |


### Differences between DexNav and PokeRadar

* When using the PokeRadar, you have to stand in a grass patch for it to work. For DexNav, you can stand anywhere although for RNG purposes, we will actually be standing outside it. Also PokeRadar usually generates 5 patches (unless they don't fit) while DexNav only 1.
* When using the PokeRadar, the species is decided when chain = 0 and then locks until the chain breaks. With DexNav you have to RNG for the slot as well (at least that's the case with the turn method that we will be using).
* When using the PokeRadar, if chain > 0, you RNG for the shininess first by activating the device, then wait in front of the patch until you reach your target frame to RNG for stats. You also see the patch glowing most of the time. In DexNav, you RNG for everything at once. You don't see the patch glowing but you see it shaking the whole time as well as some info when approaching.
* To get guaranteed IVs from PokeRadar, you have to slowly build the chain (max 60 for 3 perfect IVs), although shiny patches can be generated after chain is 1 or higher. With DexNav you can generate a 1-3IV shiny patch immediately. 
* PokeRadar doesn't have exclusive Pokemon and you can't abuse for some extra add ons like HA, Egg move, Level Boost. DexNav can get you any available Pokemon for a given location including fishing and Horde Pokemon.
* PokeRadar patch RNG is more forgiving. You can activate the Radar device directly from the bag with no frame pressure. Also your patches don't always have to fit inside the grass in order to get what you want. DexNav is way more strict. If the patch doesn't fit, the game advances to a later index attempting to find something that fits. This increases the delay (although it happens more when using the Search method), and of course makes you miss your target.


### Tiny Finder Controls

**Second Tab (Settings)**

`Shiny Charm` should be obvious.

`Grass`, `Long Grass`, `Cave`, `Water` are all different types that affect the available species.
If you know a specific Pokemon is available in a given location but you don't see in the 3rd tab, 
it's most likely due to having selected the wrong type.
For example Tentacruel in Victory Road will be visible only when you select `Water` instead of `Cave`.

If using a flute (Black/White - affects the wild's Pokemon level) select it otherwise leave it as is.

Ignore the `Noise` field for now.

`Search Level` is the number of times you have encountered the target Pokemon (shown in the DexNav screen for each Pokemon - caps at 999). Suggested value: 999.

`Chain` is the current chain length (caps at 99 then resets to 0). Suggested value: 4.

**Third Tab (Preferences)**

Select the desired species in the first combobox. 
The corresponding slot(s) will be auto selected, 
though you can still edit them manually (not recommended).

In the third combobox, fill in the rest of the filters to your preference.

`Shiny` is searching for guaranteed shiny patches only (The main reason to do DexNav RNG in the first place).

`HA` for Hidden Ability and `Egg move` for an exclusive breeding move than cannot be obtained otherwise.

`Level Boost` is for getting a +10 boost to the wild's Pokemon level (an exclamation mark will be shown in the console's lower screen when occurs).

Finally, `Potential`, is the guaranteed perfect IVs you will get for that index (caps at 3). 
Leave it to 0 if you don’t care.

### DexNav results

The `Right` and `Up` columns show the coordinates of the generated patch. Negative values, mean opposite direction 
so for example a pair of Right = -8 and Up = -3, means that you will be getting a patch 8 tiles **left** and 3 **down** from the position you will be standing at.
If there is no grass/water tile in those coordinates, you will fail your target so be careful when choosing your spot.

Yellow marked rows mean that a Pokemon will spawn successfully, otherwise they will be white (Clicking `Generate` will only show successful ones).

Sync, Slot, Species, Level, HA and Egg Move columns need no further explanation.

`Shiny` when true, means forced shiny patch. 
The row will be marked as blue only if the patch is BOTH shiny forced AND successful, otherwise will still remain white.

`Potential` was explained above.

### Chain Building

To build a DexNav chain, all you need to do is defeat or capture Hidden Pokemon.

They don't have to be DexNav exclusives like Lillipup or Zorua, they can be Zigzagoon, Poochyena etc but they have to be hidden encounters.

This means that running around without repels to trigger a wild encounter by moving in the grass, does **NOT** work.

Run around (or use the search function in the lower screen), to trigger a DexNav shaking patch.

Use a repel to prevent wild encounters and approach the Pokemon slowly using the Circle Pad then either capture or defeat it.

The chain length value is now +1.

Things that will break the chain include:

* Not encountering a hidden Pokemon that has appeared in the overworld either by leaving the area / waiting too long until it disappears / scaring it by running/walking fast towards it
* Running away from a battle

If you use the Search button to scan for hidden Pokemon and nothing is found, the chain does **NOT** break

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
This means that you need to increase the "Noise" by 2 in order to get accurate results.
For example, when you want to generate a DexNav patch in a water route, if your current spot is land, you don't need to edit the Noise, 
otherwise, if your current spot is inside the water, you may need to increase it by 2. 
This is not always the case and you need to test yourself depending on your exact tile in the map.

* In grassy areas, we saw that the possilbe ring inside where a patch can be generated, is [-9, 9] for both vertical and horizontal. 
This is not the case with special places, where the ring, is apparently affected by your exact tile on the map and surely enough, is smaller than [-9, 9].
Generally speaking, I succeeded more frequently, by aiming for indexes whose coordinates are close to 0 for either the X or Y axis.
For example, indexes with values [-7, 1] or [8, 0], are safer than indexes like [9 ,5] or [-6, 7].
If you have setup Citra, you can try multiple indexes quickly using the Date Searcher, until you find a successful one.
If you want to do this on 3ds, you should check the coordinates of your target index, 
and use the Date Searcher in order to find similar indexes with the same coordinates and test them on Citra.
If they are successful, you have high chances of succeeding on 3ds as well.
In terms of difficulty, from the easiest to the hardest ones: water routes < creepy buildings < caves < route 111

* The hidden Pokemon does not stay in the same spot but instead keeps moving constantly inside a new, specific ring. It also disapperars way easier especially if it can't move inside the ring due to your character's presence. Don't even try to build a chain in those areas. At chain 4, the Pokemon shakes literally 3 times before disappearing and you don't have enough time to approach it anyway. For whatever reason, GF decided to make this completely unfair.

### Practicing

The best places for that, are hands down the Mirage Spots (except caves of course).
They are quiet places with no NPCs, the bag advances are the standar +15 and they include large grass tables which give the user a lot of possible patch coordinates to aim for.
They also don't have DexNav exclusive Pokemon that affect the slots.

Practice, practice, practice.
Keep aiming for non shiny indexes and try to hit them. Play around with the Pcalc menus to increase/decrease the lag and use whatever works better for you.

On 3ds you can use the NTR Helper to keep track of the steps and chain length.

On Citra you can find great and early indexes easily without the need to build a chain.

Try everything that you may find useful.

### Conclusions

* Depending on what the user is looking for, this can be either harder or easier than Normal Wild RNG but generally speaking, DexNav RNG is more challenging. While you have a higher chance of triggering a patch (50% unlike 13% and 7% for wild), you also have to deal with higher delay which boosts the NPC influence. Apart from that, if you choose to rotate and not step, you have to single tap the arrow which requires precision. Normal wild is easier on this part because you can just hold down the arrow and the encounter won't be affected. As for indexes, full DexNav ones are more rare of course, but with Tiny Finder filtering the results, this is not really an issue (Don't forget the Date searcher for Citra also). Finally the slot generation is an interesting topic. Their rarity is reversed on DexNav, making slot 12 the most common, slot 11 less common etc. GF probably wanted to give users an alternative and easier way to find those 1-5% targets faster.

* Unlike a possible search method that may occur in the future, this method gives full control of almost everything. Consistency is the key, and if you want a specific flawless Pokemon, you need to have control of both RNG states (MT and TinyMT). Citra allows for more possibilities, but 3ds is most likely to remain in this state.

