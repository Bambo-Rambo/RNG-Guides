# SOS RNG

While a cool way of obtaining high IV shinies in the wild, including fully evolved underleveled ones, SOS RNG still remains one of the least famous types of RNG
since almost everything is possible with eggs nowdays.

The unstable delay (due to battle RNG), the time taken to build a decent chain as well as a few more inconsistencies, didn't help the situation either.

However, it's still my favourite gen 7 RNG type so I will try to explain my method and provide as much info as possible in this guide 
to make it consistent 95% of the time.

Please keep in mind that this is only my own approach and I will be using Citra Emulator for 2 reasons:
* It can run at full speed making the chain build process way faster.
* SOS ram reading isn't exactly stable. I made some changes in CitraRNG but Pcalc isn't gonna be updated. 
You can wait for a [Pokereader](https://github.com/zaksabeast/PokeReader) update or use Pcalc regardless but it will require some manual input.

The method itself is not actually difficult but it requires a careful and detailed setup, which varies depending on your target.

Having shiny hunted using SOS encounters in the past and/or having understood the [guide](https://www.pokemonrng.com/retail-usum-sos) in Pokemonrng.com, 
will make this guide easier to understand, but neither are necessary.
### Tools
* [Citra Emulator](https://github.com/citra-emu) (Either a Canary or Nightly build)
* [3DS RNG Tool](https://ci.appveyor.com/project/Bambo-Rambo/3dsrngtool/build/artifacts) (my fork with various enhancements and bug fixes)
* [CitraRNG](https://github.com/Admiral-Fish/CitraRNG/releases) (either the original script or [my fork](https://github.com/Bambo-Rambo/CitraRNG) which helps dealing with crashes easier)
* [3DS Time Finder](https://github.com/Admiral-Fish/3DSTimeFinder) (optional for searching high IV spreads)
* [PKHex](https://github.com/kwsch/PKHeX/releases) (for setting up your team)

### Introduction
If you have understood gen 7 egg RNG (without Masuda method or Shiny Charm) in the past, you already know that we keep accepting/rejecting eggs to advance egg indexes, 
and when reach our target **index** (which guarantees IVs, HA, gender etc), we wait in front of the Pokémon Nursery lady until reach our target **frame** to make the egg shiny.

Similarly to this, in SOS RNG we keep defeating allies to advance SOS indexes and when reach our target **index** (which guarantees species, HA etc), 
we wait before the ally appears until reach our target **frame** and make it shiny.

In other words, both egg and SOS RNG, use 2 RNG states instead of 1 which need to be manipulated separately for succeeding with the final target.

### Setting up the team

Use PKHeX to inject the following items in your bag if you don't have them already:

* Honey
* Adrenaline orb
* X accuracy
* Leppa Berry
* Cheri Berry
* Roto Boost
* Roto PP restore
* Damp Rock
* Smooth Rock
* Icy Rock

As for the steps you need to follow, the general idea of this method is:
* Use the Harvest/Leppa berry combo to prevent the caller from struggling to death
* Minimize the caller's accuracy and maximize your own evasiveness to increase the chance of stabilizing the battle delay
* Build a decent chain to increase the shiny success probability
* Use the paralyze/heal method to advance indexes 1 by 1 and reach your target consistently

The team I use myself can be found [here](https://pastebin.com/vzHEA4Zm).
I will give more details later.

Copy the contents from the above link, inject the team in your save with PKHeX (Tools -> Showdown -> Import set from clipboard), and do the following changes:

- Change Trevenant's nature to whatever you want the target Pokemon to have (Mew is the actual synchronizer but there is a bug with SOS battles that use the nature of the 1st party Pokemon instead)
- If your target is [weather slot](https://bulbapedia.bulbagarden.net/wiki/SOS_Battle#Weather-dependent_allies), 
change the **held item** and **first move** of the **2nd Mew** (nickname: *4. Weather*) depending on the case. More specifically:
  - If your target belongs to either the Poliwag/Goomy evolution families (Poliwrath/Politoed/Sliggoo etc), **do not change anything**
  - If it belongs to the Vanillite family, Mew's held item should be **Icy Rock** and first move should be **Hail**
  - If your target is Gabite, the held item should be **Smooth Rock** and first move should be **Sandstorm**

Sunny day will be necessary regardless of your target so don't remove it from the moveset.

Keep in mind that, unlike what you may have read, using super effective moves against the allies, **does NOT** affect anything.

**Never forget to restore Trevenant's Leppa Berry and Mew's Cheri Berry before and after every battle.**

### Getting Started

First of all, you obviously need to encounter the wild Pokemon which calls the desired ally.

If don't know how to RNG wild encounters, you can use this [guide](https://www.pokemonrng.com/retail-usum-wild) as reference.

* [Gen 7 Wild slots](https://sites.google.com/site/pokemonslots/gen-vii)

After understanding how to wild RNG, and when you have calibrated delay, correction and made sure you are about to encounter the correct Pokemon, 
highlight the Honey inside the bag and **create a save state just before using it**.
Depending on how rare your target is, you may need to restart the battle multiple times to refresh the SOS seed,
and having a save state just before the battle start, will speed up the process.

If you keep getting the exact same SOS seed after restoring the save state, move around the bag cursor a bit, highlight different items
and recreate the save state when Honey is highlighted again (similar to the VBlank avoidance in gen 3).

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS1.png)

The annoying part is to actually set everything up and find a SOS index that satisfies you.

Then you will be able to start building your chain and hit your target index + target frame, 
a process which is quite easy now as 3DS RNG Tool will do most of the job for you.

When the encounter starts, go to the SOS tab in CitraRNG, press *Update* to read the SOS seed, then *Pause* and **do nothing else yet**.

While leading with Trevenant, use Trick to pass the Leppa Berry to the enemy and then Skill Swap to give it "Harvest".

You have now advanced the SOS state a bit (most likely by 2 indexes unless the enemy has called for help already).

Press *Update* again and if the values of *Current Seed* and *Index* are updated normally, 
skip to the next [step](https://github.com/Bambo-Rambo/RNG-Guides/blob/main/SOSRNG.md#checking-the-possible-indexes).

If you get an error message **"Exiting an infinite loop. Retry the battle and start updating before taking any actions."**,
manually edit the Initial Seed value (in the SOS tab) a bit (increase/decrease by ±1/2) and press *Update* again.

If you get the same error, repeat the process with a different edit (if you tried +1 earlier, try -1 this time etc) until you get no error.

**(Sometimes the script doesn't read the SOS seed correctly so it's impossible for it to calculate the current index thus causing the error,
something that may happen with Pcalc as well.)**

In my case, you can see that it read **FABB1D05** at first so I got the error,
but when I changed to **FABB1D04** (-1) and pressed *Update* again, it worked as intended.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS2.png)

This process is a bit tedious but necessary if you want to "save" your seed instead of restarting the battle.

It's also useful if you want to make a save state in the middle of the battle and reload it (implies knowing and manually putting the SOS seed of course).

### Checking the possible indexes

When you have confirmed your SOS seed, it's actually time to check if there are any indexes that meet your expectations.

In 3DS RNG Tool, go to "Tools" -> "Misc. RNG Tool" -> RNG -> G7 SFMT (32bit) -> SOS and set up the tool.

Set the "Length" to anything higher than 30 (unless you are not willing to maximize the chain boost) 
and the "Call rate" according to [this link](https://pastebin.com/W59vsi0H).

(When call rate = 9, it usually takes around 400 indexes to reach chain 30 so keep that in mind when setting the *Starting index* value.
If the call rate is lower, it obviously takes more)

If your target is [weather slot](https://bulbapedia.bulbagarden.net/wiki/SOS_Battle#Weather-dependent_allies), check the "Weather" box.

The "IVs" dropdown menu refers to the already perfect IVs that can occur from **main RNG**.
This practically means that if your target (shiny) frame, has at least 1 perfect IV **by default** before the SOS bonus, 
it needs to be checked in the menu so the tool can calculate accurate results.

In my case, I used 3DS Time Finder to find a frame that already has 5 perfect IVs (31/31/31/x/31/31) so the tool needs to look like this:

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS3.png)

In the "SOS2" tab, set the "Encounter Slot" according to the following links depending on the game and what exactly you are looking for:
* [Sun](https://gist.github.com/RichardPaulAstley/42fbabe24250969f22d18fe8b919c520) (Should be easy to figure out yourself for Moon)
* [Ultra Sun](https://gist.github.com/SciresM/a539739085e24af55dffdf443cb70eb2)
* [Ultra Moon](https://gist.github.com/SciresM/deecdcf5fc49fc8191a29d111643c6b6)

The rest of the filters should be self explanatory.
**Don't check the "Success Only" box yet.**

If you don't care about the exact level of your target, leave the value to 0.

I aim for a lvl 9 shiny HA Salamence with sync nature so according to the above links, 
I set the Call Rate to 9 (Bagon), while slot is 1 (1%) and Level is 9 obviously.

Press *Calculate* and if you get no results, reload the save state you created earlier just before using the honey and 
repeat the above steps from beginning (find the actual SOS seed etc).

**Note that when a new encounter starts, you need to manually clear the Initial seed value in CitraRNG by pressing the Backspace button in your keyboard.
The script will only read from ram when there is no seed already, otherwise it will try the existing one.**

If the tool finds something, the final step is to check if the index can be hit somehow.

Right click on it and press *Find Path for index*.

If you get a message **"No path found"**, try a different one.

After a few attempts trying different seeds, I found that index 307 at seed **46A28F62** is reachable from index 305.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS4.png)

Moreover, according to the tool, I need to use Thunder wave when get close to index 305, 
then I will use Trick to give the enemy my Cheri berry to heal it, it will call for help which will be ignored, 
and I am gonna land at 307 in which case, all I will have to do is wait until reach my shiny frame.

### Battle setup

Enough talking, time to set everything up and start building the chain.

I have already used Trick + Skill Swap to give the enemy Bagon the Leppa Berry + Harvest and prevent it from struggling to death.

I am gonna switch to Smeargle and spam Minimize and then Flash to maximize the chance of the enemy missing its future moves.

Then I am gonna use Substitute and Baton Pass to the **first** Mew (nickname: *3. Chain*).

False Swipe is necessary to make Bagon's health red and maximize the call-for-help chance, 
while Adrenaline orb is necessary so it will keeping calling for help constantly.

Also I am gonna use X accuracy once (for future Thunder wave usage), and few Roto Boosts to prevent an early substitute break
(especially when dealing with high level enemies).

All 3 Mews have Baton Pass so the substitute along with stat changes will be preserved through the whole process (helpful for stable delay).

If you are on Citra, don't forget to create new saves states every once in a while just in case something bad happens 
(if there is only 1 Pokemon on the field, you may knock it out accidentally and end the battle).

### Delay calculation

Speaking of which, since I know that my last action will be a usage of Adrenaline orb (just for advancing to the final turn, nothing will actually happen), 
I will create the same conditions in an earlier index and make a test to find the exact delay value 
(hopefully Bagon will miss both during the calibration as well as during the final turn).

At index 152, its last call (from 150) failed so according to 3DS RNG Tool,
after using the Adrenaline orb to move on the next turn, a new Bagon will surely appear whose stats I am gonna check to find my delay.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS5.png)

(Note that when Adv. = 1 the Pokemon will not call for help at all, 
when Adv. = 2 the Pokemon will call for help but will get no response 
and when Adv. > 2 the Pokemon will call for help which will be successful).

In the main window, check the *SOS call* box and put your SOS initial Seed, current index and chain length.
If you get no results at all, make sure that the correct ally is selected.

Uncheck the *Consider delay* box and don't forget to change the NPC value to 0 since they don't affect anything during the battle.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS6.png)

Notice how frames 20349-20351 have some weird marks.

This practically menas that state 20350 is gonna remain the same for 5 frames and state 20351 for 30 frames.

This can be abused for good purpose if those marks exist inside your shiny target frames to increase the shiny range but otherwise they should be avoided, 
especially when calibrating delay so I am gonna calibrate at frame 20360.

### Final Steps - Hitting the taget ally

After knocking out some Bagons, I reached index 298.

This is very close to 305 so I should proceed with final steps.

Using Thunder wave here, will prevent Bagon completely from calling new allies, 
while the SOS index keeps advancing by 1 every turn.

Don't forget that if there are 2 Pokemon on the field, thunder wave needs to be used before knocking out the second one, 
otherwise the first one may call for help, suceed, and overtake your target index.

**Important: If your target Pokemon is weather slot, you obviously have to set the weather by "baton passing" to the 2nd Mew first (nickname: *4. Weather*).
If the enemy has already set the weather itself using one of its own moves (Poliwhirl may use Rain Dance for example), 
its effect may end just before your target (Poliwrath/Politoed) appears which will fail the slot.
For this reason, I highly recommend resetting the weather again by yourself using Sunny Day first, 
then Rain Dance (or whatever move depending on the weather you want to set)**

After paralyzing it, I will finaly Baton Pass to the 3rd and final Mew (the one with no nickname) and before anything, 
I am gonna use Skill Swap to send away the Harvest ability I gave it earlier and prevent it from restoring the berry 
which would practically have 50% chance of messing with the delay.

After wasting 7 more battle turns by using Adrenaline orbs, 
I reached index 305 so now I have to use "Trick" and give the enemy Bagon my Cheri berry to heal its paralyze status.

I expect it to call for help which will be ignored, and jump to index 307.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS7.png)

There we go!

I landed at my target index (307) and since there is no ally on the field, 
all I have to do now is wait until reach my target (shiny) frame and then waste the turn by using one last Adrenaline orb.

Notice how those weird symbols exist inside my shiny range so there is no chance I am missing this shiny.

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS8.png)

![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS9.png)
![](https://raw.githubusercontent.com/Bambo-Rambo/RNG-Guides/main/Images/SOS/SOS10.png)


